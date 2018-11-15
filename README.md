# NASR-airport-parser

NASR-airport-parser is a simple utility for parsing airport data from the FAA's 28-day subscription (available [here](https://www.faa.gov/air_traffic/flight_info/aeronav/aero_data/NASR_Subscription/)).

## Getting Started

### Usage

Clone the repository

```
git clone https://github.com/andydeforest/nasr-airport-parser.git
```

Create a file and import the parser. The parser takes the location of the `APT.txt` file as a parameter. Example:

```php
require './src/Parser.php';

$parser = new Parser('./APT.txt');

$parser->forEach(function($airport) {
	$name = $airport->getName();
});
```
### Available Airport Methods

| Method           | Returns | Description| Example|
|------------------|---------|------------|--------|
|getIcao()|string|Gets the ICAO code for the airport|KORD
|getIdentifier()|string|Gets the FAA identifier for the airport|ORD
|getName()|string|Gets the name of the airport|CHICAGO O'HARE INTL
|getCity()|string|Gets the city the airport is in|CHICAGO
|getCounty()|string|Gets the county the airport is in|COOK
|getState()|string|Gets the state the airport is in|ILLINOIS
|getLatitude()|float|Gets the latitude of the airport in decimal format|41.974521944444
|getLongitude()|float|Gets the longitude of the airport in decimal format|-87.906597222222
|getElevation()|float|Gets the elevation of the airport|680.0
|getType()|string|Gets the type of airport|AIRPORT
|getRegionCode()|string|Gets the FAA region code for the airport|AGL
|getOwnership()|string|Gets the ownership of the airport|PUBLICLY OWNED
|getArtcc()|string|Gets the ARTCC code for the governing ARTCC body|ZAU
|hasControlTower()|bool|Gets whether or not the airport has a control tower|true
|getCtaf()|string|Gets common traffic advisory frequency for the airport|122.8

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details