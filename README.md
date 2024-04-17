# Node.js server with MySQL Template

## Table of Contents

- [Dependencies](#dependencies)
- [Installation](#installation)
- [API specification](#API_specification)

## Dependencies

- dotenv
- express
- mysql2

## Installation

1. Clone the repo to your local machine
2. Run `npm i`
3. Create `.env` file, set up environment variables according to your Azure Database resource:<br>
   `MYSQL_HOST = HostIPAddress/Domain`<br>
   `MYSQL_USER = Username`<br>
   `MYSQL_PASSWORD = YourPassword`<br>
   `MYSQL_DATABASE = DatabaseName`<br>
   `PORT = 4000`
4. Get SSL Certificate `DigiCertGlobalRootCA.crt.pem` from Azure Database resource
5. Start the server: `npm run dev`

## API specification<a name = "api-spec"></a>

Your API should conform to the following specifications.

### Show countries

Get a list of all properties currently listed.

**URL** : `/`

**Method** : `GET`

```json
[
  {
    "Code": "ABW",
    "Name": "Aruba",
    "Continent": "North America",
    "Region": "Caribbean",
    "SurfaceArea": 193,
    "IndepYear": null,
    "Population": 103000,
    "LifeExpectancy": 78.4,
    "GNP": 828,
    "GNPOld": 793,
    "LocalName": "Aruba",
    "GovernmentForm": "Nonmetropolitan Territory of The Netherlands",
    "HeadOfState": "Beatrix",
    "Capital": 129,
    "Code2": "AW"
  },
  {
    ...
  }
  ,
  ...
]
```

---

### Show the information about a specific country

Get a single country.

**URL** : `/country/:countryname`

**Method** : `GET`

**Content example**

Request: `GET country/new%20zealand`

```json
[{
"Code": "NZL",
"Name": "New Zealand",
"Continent": "Oceania",
"Region": "Australia and New Zealand",
"SurfaceArea": 270534,
"IndepYear": 1907,
"Population": 3862000,
"LifeExpectancy": 77.8,
"GNP": 54669,
"GNPOld": 64960,
"LocalName": "New Zealand/Aotearoa",
"GovernmentForm": "Constitutional Monarchy",
"HeadOfState": "Elisabeth II",
"Capital": 3499,
"Code2": "NZ"
}]
```



### Find the total population of a continent

Return a String with the number of the continent.

**URL** : `/population/:continent`

**Method** : `GET`

**Content example**

Request: `GET country/new%20zealand`

```string
`The total population of asia is 3705025700`
```
