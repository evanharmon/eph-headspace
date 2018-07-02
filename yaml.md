# Always check for errant ,
This is not JSON, do not end a line with a , comma

# String
`allow: !!str true`

# Boolean
`EBSEnabled: !!bool true`

# Integer
`Iops: !!int 0`

# Null
`value: !!null null`

# Short Form
`!FindInMap [ ]`
equivalent to
`Fn::FindInMap: [ ]`

# Basic Array
```
- one
- two
```

# Property with Array of items
```
AllowedValues:
	- t2.micro
		- m1.small
			- m1.large

			# Basic Object
			## Two Space Indentation
				Name: Instance 2

				# Nested Objects
				Properties:
					KeyName: testPair
```

# PARSERS
http://www.yamllint.com/
http://yaml-online-parser.appspot.com/

# Exclude line breaks from content
```
!!str "line feed, \
      is ignored"

      # Include line breaks in content
      !!str "line one then, \n\
            line two"
```
