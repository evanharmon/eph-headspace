# GOLANG PROTOBUF JSON EXAMPLE
Useful for debugging. JSON is a weaker format though

## PROTO FILE
```golang
// storage-service/proto/storage/storage.proto
syntax = "proto3";

package go.micro.srv.storage;

option go_package = "storagepb";

message Bucket {
  string name = 1;
}
```

## MAIN FILE
```golang
// Package main provides the cli tool
package main

import (
	"fmt"
	"io/ioutil"
	"log"

	"github.com/evanharmon/eph-music-micro/storage-service/proto/storage"
	"github.com/golang/protobuf/jsonpb"
	"github.com/golang/protobuf/proto"
)

func main() {
	sb := &storagepb.Bucket{Name: "receipts"}
	writeToFile("test.json", sb)
	fmt.Println(sb)

	sb2 := &storagepb.Bucket{}
	readFromFile("test.json", sb2)
	fmt.Println(sb2)

	sb2String := toJSON(sb2)
	fmt.Println(sb2String)

	sb3 := &storagepb.Bucket{}
	fromJSON(sb2String, sb3)
	fmt.Println("Successfully created proto struct from JSON", sb3)
}

func writeToFile(fname string, pb proto.Message) error {
	out, err := proto.Marshal(pb)
	if err != nil {
		log.Fatalln("Can't serialize to bytes", err)
		return err
	}

	err2 := ioutil.WriteFile(fname, out, 0644)
	if err2 != nil {
		log.Fatalln("Can't write to file", err2)
	}

	fmt.Println("File written to disk")
	return nil
}

func readFromFile(fname string, pb proto.Message) error {
	in, err := ioutil.ReadFile(fname)
	if err != nil {
		log.Fatalln("Error reading from file", err)
		return err
	}

	err2 := proto.Unmarshal(in, pb)
	if err2 != nil {
		log.Fatalln("Error proto unmarshal'ing to struct", err2)
		return err2
	}

	return nil
}

func toJSON(pb proto.Message) string {
	marshaler := jsonpb.Marshaler{}
	out, err := marshaler.MarshalToString(pb)
	if err != nil {
		log.Fatalln("Error converting to JSON", err)
		return ""
	}

	return out
}

func fromJSON(in string, pb proto.Message) {
	err := jsonpb.UnmarshalString(in, pb)
	if err != nil {
		log.Fatalln("Failed to unmarshal JSON in to pb struct", err)
	}
}
```
