Pick'n'treat
===================
2015-10-15




Problem
-------------

You want to collect data from your website, that you wish to analyse later,
but you don't want to use an expensive mechanism that would slow down your whole application.






Solution
--------------

Log the data that you want in a raw format in a file.
Then using a midnight cron job, convert the file into data in a database.



If the data you want to collect is not already in some logs like the apache log for instance, 
you can use the 
[QuickLog](https://github.com/lingtalfi/QuickLog) 
object to collect any data that you want from your application.



Here is a quick example that I used for one of my websites:
(you need any [BSR-0](https://github.com/lingtalfi/BumbleBee/blob/master/Autoload/convention.bsr0.eng.md) autoloader to make it work)


(init of my application)
```php
QuickLog::inst()->setDir('/path/to/log.d');
```


(some file in my application)
```php
// Here, that's my app business logic, basically I capture the user searches in a file for later analysis
if (
    array_key_exists('search', $qParams) ||
    array_key_exists('search2', $qParams) ||
    array_key_exists('search3', $qParams)
) {
    QuickLog::inst()->addEntry(date('Y-m-d H:i:s') . '::' . $_SERVER['REQUEST_URI'], 'searches');
}
```


You can also send you an email when the log is rotated, more about this in the [QuickLog docs](https://github.com/lingtalfi/QuickLog)