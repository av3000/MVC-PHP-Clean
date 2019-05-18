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

<h6> After model is created you can use it in your page. </h6>

//<?php

class YourController extends Controller {

  public function contructor(){
  
    $this->YourNewModel = $this->model('YourModelFromModelsFolder');

  }
  
  public function yourpage(){

  $YourData = $this->YourNewModel->getData();
  
  $data = [ 
  
    'title' => 'Welcome',
    
    'newData' => $YourData 
  ];
  
  $this->view('YourController/yourpage', $data);
  
  }
  
}

//?>

<h4> Step-3: Use data in your page </h4>

<h6> We need to go one folder up into views folder </h6>
"cd .." <br/>
"cd views" <br/>

<h6>Inside of views folder I suggest to create seperate folder </h6>
"mkdir YourPages" <br/>
"cd YourPages" <br/>
"touch yourpage.php" <br/>

<h6>Inside of yourpage we can use to show data from the "YourController.php" </h6>

// <?php

echo $data['title']; 

echo $data['newData'];

//?> 

// ?>



<h2> Will be updated. </h2>
<h2> Last update 2019-05-18. </h2>

