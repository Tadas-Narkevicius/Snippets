## Mysql connection
```
$db = mysqli_connect("localhost"," "," ","staff");

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
## Pdo connection
```
$servername = "localhost";
$username = " ";
$password = " ";

try {
    $conn = new PDO("mysql:host=$servername;dbname=staff", $username, $password);
    // set the PDO error mode to exception
    $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
    echo "Connected successfully"; 

    $rezults = $conn->query('SELECT * FROM staff.staff');
}

catch(PDOException $e){
    echo "Connection failed: " . $e->getMessage();
}

foreach($rezults as $row) {
    echo "<br>" . $row['id'] . " "; 
    echo $row['name'] . " "; 
    echo $row['lastname'] . " "; 
}
```
