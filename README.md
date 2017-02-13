# Check-realworldemailvalidation
This script will help to find out whether the given email id is actually exist or not in the real world

1) Download Scripts 
2) crete a mail.php file or open your existing php file then add following code and change SMTP email ID.

          // include SMTP Email Validation Class
          require_once('smtp_validateEmail.class.php');

          // the email to validate
          $email = $_REQUEST['emailID'];//'hadi7cseuoda@hotmail.com';
          // an optional sender
          $sender = ''; // Your smtp email ID like youyou@yourdomain.com
          // instantiate the class
          $SMTP_Validator = new SMTP_validateEmail();
          // turn on debugging if you want to view the SMTP transaction
          //$SMTP_Validator->debug = true;
          // do the validation
          $results = $SMTP_Validator->validate(array($email), $sender);
          // view results
          echo ($results[$email] ? 'valid' : 'invalid');

          // send email? 
          if ($results[$email]) {
            //mail($email, 'Confirm Email', 'Please reply to this email to confirm', 'From:'.$sender."\r\n"); // send email
          } else {
            //echo 'The email addresses you entered is not valid';
          }
          
3) the submited form is 

<!DOCTYPE html>
<html>
<body>

<form action="action_page.php">
 
  Email ID:<br>
  <input type="text" name="emailID" value="">
  <br><br>
  <input type="submit" value="Submit">
</form> 

<p>If you click the "Submit" button, the form-data will be sent to a page called "mail.php" or your selected php file.</p>

</body>
</html>


Note:- If you have any question then please have your comments, i will try to answers very shortly


  
