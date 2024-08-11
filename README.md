<?php
include 'config.php';

if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $name = $_POST['name'];
    $age = $_POST['age'];
    $experience = $_POST['experience'];

    $sql = "INSERT INTO maids (name, age, experience) VALUES ('$name', '$age', '$experience')";

    if ($conn->query($sql) === TRUE) {
        echo "New maid added successfully";
    } else {
        echo "Error: " . $sql . "<br>" . $conn->error;
    }
}

$conn->close();
?>

<form method="post" action="add_maid.php">
    Name: <input type="text" name="name" required><br>
    Age: <input type="number" name="age" required><br>
    Experience (in years): <input type="number" name="experience" required><br>
    <input type="submit" value="Add Maid">
</form>
