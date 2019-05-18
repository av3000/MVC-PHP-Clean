<h1> MVC-PHP-Clean </h1>
<p> Welcome to the documentation </p>
<h3> Setup </h3>

Go to ->public->.htaccess 
Line 4 "RewriteBase" Change your directory.

Create your database 

Go to ->app->config->config.php 
Line 3 - 6 Change your database settings Line 11 Change your root url path.

You can find all used libraries in ->app->libraries directory.

<h3> Use database </h3>

<h4> Step-1: Create a model </h4>

Create models folder:  <br/>
"cd MVC-PHP-Clean/app" <br/>
"mkdir models" <br/>
"cd models" <br/> 
"touch YourModel.php" <br/>
"./YourModel.php" <br/>
<br/>

//<?php

class YourModel {

  private $db;
  
  public function constructor(){
  
    $this->db = new Database;
  
  }
  
  public function getData(){

  $this->db->query("SELECT * FROM YourTable");
  
  return $this->db->resultSet();

  }

}

//?>

<h4> Step-2: Use model in a controller </h4>

"cd .." <br/>
"cd controllers" <br/>
use existing one 
"./Pages.php" <br/>
or create your own controller
"touch YourController.php" <br/>

<h6> Inside of controller add: </h6>

//<?php

class YourController extends Controller {

  public function contructor(){
  
    $this->YourNewModel = $this->model('YourModelFromModelsFolder');

  }
  
}

//?>

<h6> After model is created you can use it for example, in your index page. </h6>

//<?php

class YourController extends Controller {

  public function contructor(){
  
    $this->YourNewModel = $this->model('YourModelFromModelsFolder');

  }
  
  public function index(){

  $YourData = $this->YourNewModel->getData();
  
  $data = [ 
  
    'title' => 'Welcome',
    
    'newData' => $YourData 
  ];
  
  $this->view('', $data);
  
  }
  
}

//?>
