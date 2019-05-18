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

}

//?>


