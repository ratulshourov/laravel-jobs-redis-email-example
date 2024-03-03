
## Create Job and Email Redis Run 
## php artisan make:mail SendTestMail --markdown=emails.testmail
- Then Mailtrap configure .env file set email information set from address also 
- then in the web.php file
- by default route 
-  \Mail::to('abc@gmail.com')->send(new \App\Mail\SendTestMail());  
## php artisan make:job SendEmailJob
- Then change .env QUEUE_CONNECTION sync to database

## php artisan queue:table
- Create a migration file for the jobs automatically from the above command
- php artisan migrate:fresh
- now set the below in the web.php default route 
-  dispatch(new \App\Jobs\SendEmailJob());
## php artisan queue:listen
- above code start the queue







