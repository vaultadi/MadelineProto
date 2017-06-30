---
title: users.getUsers
description: users.getUsers parameters, return type and example
---
## Method: users.getUsers  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|id|Array of [InputUser](../types/InputUser.md) | Yes|


### Return type: [Vector\_of\_User](../types/User.md)

### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
if (isset($token)) { // Login as a bot
    $MadelineProto->bot_login($token);
}
if (isset($number)) { // Login as a user
    $sentCode = $MadelineProto->phone_login($number);
    echo 'Enter the code you received: ';
    $code = '';
    for ($x = 0; $x < $sentCode['type']['length']; $x++) {
        $code .= fgetc(STDIN);
    }
    $MadelineProto->complete_phone_login($code);
}

$Vector_of_User = $MadelineProto->users->getUsers(['id' => [InputUser], ]);
```

Or, if you're into Lua:

```
Vector_of_User = users.getUsers({id={InputUser}, })
```
