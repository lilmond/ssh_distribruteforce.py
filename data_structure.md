# Login payload structure

## Login as a bot
```python
{
    "op": "LOGIN",
    "data": {
        "type": "BOT",
        "hostname": "bot1"
    }
}
```

## Login as a user
```python
{
    "op": "LOGIN",
    "data": {
        "type": "USER",
        "username": "noob123",
        "password": "password123"
    }
}
```

## Login as an admin
```python
{
    "op": "LOGIN",
    "data": {
        "type": "ADMIN",
        "username": "admin123",
        "password": "password123"
    }
}
```



# Commands And Control

## Bot Commands OP Codes

This are the commands the bot can execute on the server.

### GET_TARGETS

This is used when a bot has newly connected to the server.
When the server responds, the bot will initialize the attacks on the targets based on the hostnames, if there is.

```python
{
    "op": "GET_TARGETS",
    "data": None
}
```

#### Response:

```python
{
    "op": "TARGET_LIST",
    "data": {
        "hostnames": ["192.168.254.101", "192.168.254.102", "192.168.254.103"],
        "usernames": ["root", "user"],
        "password": ["password1", "password2", "password3"]
    }
}
```

### PASSWORD_FOUND

The bot sends this command to the server when it cracks an SSH server's password.

```python
{
    "op": "PASSWORD_FOUND",
    "data": {
        "hostname": "192.168.254.101",
        "username": "root",
        "password": "password1"
    }
}
```

### RESPONSE:
```python
None
```
