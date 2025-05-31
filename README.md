
# Lightweight VIN Decoder for PHP 8+

Decode vehicle brand, model, year, country and region from a VIN number using a fast, local PHP library — no external API calls, no rate limits.

## Usage

```php
use Vinfast\Vin;

$vin = new Vin('W0L0TGF487G011234');

echo $vin->decodeBrand();   // Opel
echo $vin->decodeModel();   // Astra (if available in VDS database)
echo $vin->decodeYear();    // 2007
echo $vin->decodeCountry(); // Germany
echo $vin->decodeRegion();  // Europe

```

## VDS Database

Most common VDS codes matched to popular models are included by default. You can override the database with your own file:

```php
$vin->setVdsDataFilePath('/path/to/your/vds.php');
```

## Testing

Run all tests and check coverage (100%):

```bash
composer test
composer test:cover
```
