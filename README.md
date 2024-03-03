
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

## Now its time to work on redis server

- Open PowerShell as Administrator and run this command to enable Windows Subsystem for Linux (WSL):
    - Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux

## Launch Microsoft Windows Store:
  -  install ubuntu   from microsoft store
## After Installing Ubantu on Windows machine open ubuntu and below commad execute one by one for redis work

- sudo apt-add-repository ppa:redislabs/redis
 - sudo apt-get update
 - sudo apt-get upgrade
 - sudo apt-get install redis-server

## After installing redis server for check 
- redis-cli

 - sudo service redis-server start
 - sudo service redis-server stop
 - sudo service redis-server restart


## Then modify .env  QUEUE_CONNECTION =redis


## Then install redis by using commad promt in your laravel project 

- composer require predis/predis

## Then go to config/databas.php file modufy it 
- 'redis' => [

  -      'client' => env('REDIS_CLIENT', 'phpredis') Replace IT phpredis To predis

## Now again start your job again 
- php artisan queue:listen 

## Thank You For your time good day






