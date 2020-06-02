# NODE KNEX

## Insert
`db("users").insert(data);`

## Update
`db("users").where("id", id).update({ field1: 5 });`

## Delete
`db("users").where("id", id).del();`

## Count
refer to result as result[0].cnt
`db("users").count("id as cnt");`

## Join
`knex.from('users').innerJoin('accounts', 'users.id', 'accounts.user_id')`
