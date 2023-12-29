
## golpe

### calor
When you have some text, how [can](http://gool.com) you choose a typeface? Many people—professional designers included—go through an app’s font menu until we find one we like. But the aim of this Google Fonts Knowledge module is to show that there are many considerations that can improve our type choices. By setting some useful constraints to aid our type selection, we can also develop a critical eye for analyzing type along the way.

#### codigo

texto aleatorio 

```cpp
// Función para manejar la ruta "/register"
void handleRegister(const http_request& request) {
    // Configura la conexión a la base de datos MySQL
    sql::mysql::MySQL_Driver driver;
    std::unique_ptr<sql::Connection> con(driver.connect("tcp://127.0.0.1:3306", "username", "password"));
    std::unique_ptr<sql::Statement> stmt(con->createStatement());

    // Extrae el nombre de usuario y la contraseña del cuerpo de la solicitud
    auto jsonBody = request.extract_json().get();
    std::string username = jsonBody["username"].as_string();
    std::string password = jsonBody["password"].as_string();

    // Encripta la contraseña utilizando SHA256
    std::string hashedPassword = encryptSHA256(password);

    // Inserta el nuevo usuario en la base de datos
    stmt->execute("INSERT INTO users (username, password) VALUES ('" + username + "', '" + hashedPassword + "')");

    // Responde con el mensaje de éxito
    request.reply(status_codes::Created, "User registered");
}
```


```python
# comentario en python
@login_manager.user_loader
def load_admin_or_user(id):
    admin = Admin.query.get(int(id))
    users = Users.query.get(int(id))
    if users:
        return users
    else:
        return admin
```

```js
{ 
    "marca":"nissan",
    "modelo":"tsuru",
    "año": 2021,
    "versiones": ["estandar","automático"],
    "Es nuevo": false
}
```

```css
/* comentarios es css */
.k{
  font-weight: bold;
  color: chartreuse;
}
```

```html
<!doctype html>
<html lang="en">
  <head>
    <!-- cometario -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Bootstrap demo</title>
  </head>
  <body>
    <h1>Hello, world!</h1>
  </body>
</html>
```


```sql
ALTER TABLE producto CHANGE precio precios DECIMAL(18,2) NOT NULL;
```
