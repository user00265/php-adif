# PHP ADIF Parser
Simple Ham Radio ADIF parser by KJ4IWX

## Usage
Simply include the file adif_parser.php and create a new ADIF_Parser and use `feed($string)` to give it a string or `load_from_file('/path/to/log.adi')` to read a file.

`get_record()` returns an array with the field as the key. You can view the possible fields here. If the array is empty that means that there are no more records to process.
```php
include 'adif_parser.php';

$p = new ADIF_Parser;
$p->load_from_file("test.adi");
$p->initialize();

while($record = $p->get_record())
{
	if(count($record) == 0)
	{
		break;
	}

echo $record["call"]."<br>";
}
```
