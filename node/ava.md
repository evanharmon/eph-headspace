# AVA

## Run Tests
`$ ava`

## Using supertest
use await and do not call .end()
```
test('signup:Success', async t => {
  t.plan(2);

  const res = await request(makeApp())
    .post('/signup')
    .send({email: 'ava@rocks.com', password: '123123'});

  t.is(res.status, 200);
  t.is(res.body.email, 'ava@rocks.com');
});
```

## Test an error
```
test('new stack pop should throw error', t => {
  const s = new Stack();
  const error = t.throws(() => {
    s.pop();
    },
    /Stack is empty/
  );
  t.is(error.message, 'Stack is empty');
});
```

## Auto Pass a Test
`test(`First Test`, t => t.pass());`
