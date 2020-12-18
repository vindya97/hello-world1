# hello-world1
hiiiii
hi im vindya

//php backend
 <?php

    if(isset($_POST['btnsubmit']))
    {
        $name=$_POST['txtname'];
        $password=$_POST['txtpassword'];

        $con = mysqli_connect("localhost","root","","cakemaster");

        if(!$con)
        {
            die("cannot connect to the server");
        }
       // $sql= "INSERT INTO `users`(`Name`, `Password` ) VALUES ('".$name."','".$password."');";

        $sql= "SELECT * FROM `users` WHERE `Name`='".$name."' and `Password` = '".$password."'";
    
        $result=mysqli_query($con,$sql);

        if(mysqli_num_rows($result)>0){

            $valid=true;
        }else{
            $valid=false;
        }
        if($valid)
        {
            echo "<script type=\"text/javascript\">window.alert('successfully login');</script>";
        }
        else{

            echo "<script type=\"text/javascript\">window.alert('please enter correct password');</script>";
        }

}

    
    
    
    ?>
