# NODE TESTING

## Errors
regex check for error objects without causing match[1] errors
```
const errCheck = /Error/g.exec(key);
should.exist(errCheck);
```

## MOCHA
" CLI stops after first failure
`$ --bail`

## Run a Single Describe or It test
Do not have more than one .only in your file - you'll get errors and die
`describe.only()`
`it.only()`

## Skip a Test
`describe.skip()`
`it.skip()`

## Generators and Describe functions must use co.wrap
no yield functions in describe open area
```
describe("", function (){
  let test1;

  before(co.wrap(function* (){
     const first = yield first();
     test1 = first
  }));
  it("",
     co.wrap(function* ({
     })
  );
});
```

## Check For HTML Value
```
const errMsg = res.text.indexOf("Wrong password");
should(errMsg).be.greaterThan(0);
```

## Variable Shadowing Errors
Make sure object properties are set in `before()` or inside `it()`
Ex: settings.defaultUrl

## ShouldJS Check Query Param
```
const url = URL.parse(res.headers.location, true);
should(url.query).have.ownProperty("SAMLRequest");
```
