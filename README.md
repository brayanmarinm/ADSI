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
