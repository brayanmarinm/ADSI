# ADSI

class conexion {
    
    private $host = "127.0.0.1";
    private $usuario = "root";
    private $pass = "123456";
    private $puerto = 3306;
    private $bdname = "usuarios";
    private $conex;
    
    
    public function __construct(){
    $this->conex = new mysqli( $this->host , $this->usuario , $this->pass, $this->bdname, $this->puerto);
    if ($this->conex->connect_errno) {
    echo "Fallo al contenctar a MySQL: (" . $this->conex->connect_errno . ") " . $this->conex->connect_error;
    }

    echo $mysqli->host_info . "\n Se ha conectado. <br><br>";
    }
    
    public function ejecutar($sentenciainput){
        $this->conex ->query($sentenciainput);
        $resultado = $this->conex->affected_rows;
        return $resultado;
    }
}

<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8"> 
        <title>Ejercicio Conexión</title>
    </head>
    
    <body>
        <?php
        // put your code here
        ?>
        
        <form action="control.php" method="POST">
            Nombres: 
            <input type="text" name="nombres" placeholder="Escriba sus nombres"><br><br>
            Apellidos: 
            <input type="text" name="apellidos" placeholder="Escriba sus apellidos"><br><br>
            Cédula: 
            <input type="number" name="cedula" placeholder="Ingrese su cédula"><br><br>
             Usuario: 
            <input type="text" name="usuario" placeholder="Escriba su usuario"><br><br>
            Contraseña
            <input type="password" name="contrasena" placeholder="Ingrese su contraseña"><br><br>
            <input type="submit" value="Enviar">
            <input type="reset" value="Borrar">
        </form>
    </body>
</html>

