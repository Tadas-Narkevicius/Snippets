## Mysql connection
```
$db = mysqli_connect("localhost","Tadas","mantas411","staff");

if ($db->connect_error) {
    die("Connection failed: " . $db->connect_error);
}

$result = $db->query("SELECT * FROM staff.staff");

while($row = $result->fetch_assoc()) {
    echo "<pre>";
    var_dump($row);
    echo "</pre>";
}
$db->close();
die();
```
