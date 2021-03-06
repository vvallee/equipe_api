# Accounting API

> Use this API if you want to fetch all accounting information from Equipe.

## Authentication

Login to your account. Visit you profile page and click show API-Key. This key should be set in the X-API-KEY header on every request.

## Shows

First, find out which show to get request the data from.

`GET /organizers/:organizer_id/meetings.json`

###### Example JSON request

```json
[
  {
    "id": 1961,
    "name": "Dressage International Horse Show",
    "starts_on": "2016-08-08",
    "ends_on": "2016-08-14",
    "logo_id": "10000",
    "logo_group": "svrf"
  }
]
```

*Use the `show_id` in the following requests*

## People

This will return all people within a show.

`GET /meetings/:show_id/people.json` 

Alternative path is `/meetings/:show_id/people/receivable.json`, `/meetings/:show_id/people/payable.json` or `/meetings/:show_id/people/zero_balance.json`

###### Example JSON request

```json
[
  {
    "rnr": 10013,
    "internet_rnr": null,
    "name": "Jitendarjit Singh Ahluwalia",
    "name_order": "Ahluwalia Jitendarjit Singh",
    "address": "",
    "zipcode": "",
    "city": "",
    "cell_phone": "",
    "horse_names": "Akira",
    "horse_pm": false,
    "country": "IND",
    "knr": null,
    "logo_id": "IND",
    "logo_group": "flags48",
    "club_name": null,
    "person_pm": false,
    "horse_ids": [
      10016
    ],
    "person_no": "1955",
    "rlic": "",
    "fei_id": "10069973",
    "pm": "",
    "economy_pm": "",
    "ankomst": false,
    "epost": "",
    "company": "",
    "address_country": "",
    "orgnr": "",
    "iban": "",
    "bic": "",
    "bank": "",
    "holder": "",
    "bg_pg": "",
    "mobil": "",
    "telefon": "",
    "dagtele": "",
    "invoice_no": null,
    "invoice_closed": false
  }
]
```

#### Person

Attribute | Type | Description
--- | --- | ---
rnr | integer | Primary key, person id
name | text | Name
name_order | text | Last name, First name
address | string | Street adress
zipcode | string | Postal code
city | string | City
address_country | string | Country
horse_names | text | Related horses (where person is payer or rider)
horse_ids | integer | Related horse ids  (where person is payer or rider)
horse_pm | boolean | Has notes on horse
country | string | Nation
knr | integer | Knr
logo_id | string | Logo id
logo_group | string | Logo group
club_name | string | Club
person_pm | boolean | Has notes on person
person_no | string | Birthday
rlic | string | License
fei_id | string | FEI ID
pm | text | Notes
economy_pm | text | Internal invoice notes
ankomst | boolean | Arrived
epost | string | Email
cell_phone | string | Cell phone
telefon | string | Home Phone
dagtele | string | Work Phone
company | string | Company
orgnr | string | VAT No
iban | string | IBAN No
bic | string | SWIFT/BIC Code
bank | string | Bank Name
holder | string | Account Holder
bg_pg | string | Account Number
invoice_no | integer | Invoice no
invoice_closed | boolean | Invoice closed, locked for changes

*Use the primary key `person_id` in the following requests*

## Economies

This will return the complete invoice-data in json. The data is self-descriptive. 

`GET /meetings/:show_id/people/:person_id/economies.json`


###### Example JSON request

```json
{
  "economies": [
    {
      "id": 10042,
      "fee_type": "entry",
      "rnr": 10022,
      "realrnr": 10022,
      "hnr": 10064,
      "qty": 1,
      "description": "Entry fee, CSI5*, Manure disposal fee",
      "vat": 21,
      "amount": 48.4,
      "total": 48.4,
      "horse_name": "Elle Dorado",
      "horse_num": 317,
      "removable": false
    },
    {
      "id": 10042,
      "fee_type": "entry",
      "rnr": 10022,
      "realrnr": 10022,
      "hnr": 10064,
      "qty": 1,
      "description": "Entry fee, CSI5*, MCP",
      "vat": 0,
      "amount": 25,
      "total": 25,
      "horse_name": "Elle Dorado",
      "horse_num": 317,
      "removable": false
    },
    {
      "id": 10042,
      "fee_type": "entry",
      "rnr": 10022,
      "realrnr": 10022,
      "hnr": 10063,
      "qty": 1,
      "description": "Entry fee, CSI5*, Manure disposal fee",
      "vat": 21,
      "amount": 48.4,
      "total": 48.4,
      "horse_name": "H&M Carat Desire",
      "horse_num": 316,
      "removable": false
    },
    {
      "id": 10042,
      "fee_type": "entry",
      "rnr": 10022,
      "realrnr": 10022,
      "hnr": 10063,
      "qty": 1,
      "description": "Entry fee, CSI5*, MCP",
      "vat": 0,
      "amount": 25,
      "total": 25,
      "horse_name": "H&M Carat Desire",
      "horse_num": 316,
      "removable": false
    },
    {
      "id": 10042,
      "fee_type": "entry",
      "rnr": 10022,
      "realrnr": 10022,
      "hnr": 10062,
      "qty": 1,
      "description": "Entry fee, CSI5*, Manure disposal fee",
      "vat": 21,
      "amount": 48.4,
      "total": 48.4,
      "horse_name": "H&M Flip's Little Sparrow",
      "horse_num": 315,
      "removable": false
    },
    {
      "id": 10042,
      "fee_type": "entry",
      "rnr": 10022,
      "realrnr": 10022,
      "hnr": 10062,
      "qty": 1,
      "description": "Entry fee, CSI5*, MCP",
      "vat": 0,
      "amount": 25,
      "total": 25,
      "horse_name": "H&M Flip's Little Sparrow",
      "horse_num": 315,
      "removable": false
    },
    {
      "id": 10043,
      "fee_type": "entry",
      "rnr": 10022,
      "realrnr": 10022,
      "hnr": 10454,
      "qty": 1,
      "description": "Entry fee, CSIYH1* incl. 8yo, Stabling services",
      "vat": 21,
      "amount": 150,
      "total": 150,
      "horse_name": "H&M Joli Coeur HP",
      "horse_num": 79,
      "removable": false
    },
    {
      "id": 10043,
      "fee_type": "entry",
      "rnr": 10022,
      "realrnr": 10022,
      "hnr": 10454,
      "qty": 1,
      "description": "Entry fee, CSIYH1* incl. 8yo",
      "vat": 0,
      "amount": 126.03,
      "total": 126.03,
      "horse_name": "H&M Joli Coeur HP",
      "horse_num": 79,
      "removable": false
    },
    {
      "id": 10043,
      "fee_type": "entry",
      "rnr": 10022,
      "realrnr": 10022,
      "hnr": 10454,
      "qty": 1,
      "description": "Entry fee, CSIYH1* incl. 8yo, Manure disposal fee",
      "vat": 21,
      "amount": 48.4,
      "total": 48.4,
      "horse_name": "H&M Joli Coeur HP",
      "horse_num": 79,
      "removable": false
    },
    {
      "id": 10043,
      "fee_type": "entry",
      "rnr": 10022,
      "realrnr": 10022,
      "hnr": 10454,
      "qty": 1,
      "description": "Entry fee, CSIYH1* incl. 8yo, MCP",
      "vat": 0,
      "amount": 20,
      "total": 20,
      "horse_name": "H&M Joli Coeur HP",
      "horse_num": 79,
      "removable": false
    },
    {
      "id": 10035,
      "fee_type": "prize_money",
      "rnr": 10022,
      "realrnr": 10022,
      "hnr": 10454,
      "qty": 1,
      "description": "Prize money, Competition I - CSIYH1* Two Phases (274.5.6) 1.35m, Rk 20",
      "vat": 0,
      "amount": -40,
      "total": -40,
      "horse_name": "H&M Joli Coeur HP",
      "horse_num": 79,
      "removable": false
    },
    {
      "id": 10036,
      "fee_type": "prize_money",
      "rnr": 10022,
      "realrnr": 10022,
      "hnr": 10454,
      "qty": 1,
      "description": "Prize money, Competition II - CSIYH1* Table A (238.2.1a) 1.35m, Rk 4",
      "vat": 0,
      "amount": -400,
      "total": -400,
      "horse_name": "H&M Joli Coeur HP",
      "horse_num": 79,
      "removable": false
    },
    {
      "id": 10035,
      "fee_type": "prize_money_artist_tax",
      "rnr": 10022,
      "realrnr": null,
      "hnr": 10454,
      "qty": 1,
      "description": "Foreign tax, 18%",
      "vat": 0,
      "amount": 7.2,
      "total": 7.2,
      "horse_name": "H&M Joli Coeur HP",
      "horse_num": 79,
      "removable": false
    },
    {
      "id": 10036,
      "fee_type": "prize_money_artist_tax",
      "rnr": 10022,
      "realrnr": null,
      "hnr": 10454,
      "qty": 1,
      "description": "Foreign tax, 18%",
      "vat": 0,
      "amount": 72,
      "total": 72,
      "horse_name": "H&M Joli Coeur HP",
      "horse_num": 79,
      "removable": false
    },
    {
      "id": 10693,
      "fee_type": "extra",
      "rnr": 10022,
      "realrnr": null,
      "hnr": null,
      "qty": 1,
      "description": "Electricity",
      "vat": 21,
      "amount": 60.5,
      "total": 60.5,
      "horse_name": null,
      "horse_num": null
    },
    {
      "id": 13214,
      "fee_type": "extra",
      "rnr": 10022,
      "realrnr": null,
      "hnr": null,
      "qty": 12,
      "description": "Shavings",
      "vat": 6,
      "amount": 10.6,
      "total": 127.2,
      "horse_name": null,
      "horse_num": null
    }
  ],
  "vat_of_summaries": [
    {
      "description": "VAT 21% (333,97 € net / 404,10 € gross) 70,13 €"
    },
    {
      "description": "VAT 0% (221,03 € net / 221,03 € gross) 0,00 €"
    },
    {
      "description": "VAT 6% (120,00 € net / 127,20 € gross) 7,20 €"
    }
  ],
  "person": {
    "invoice_no": 147,
    "invoice_closed": false,
    "name": "Jon Stenqvist",
    "total": 391.53,
    "total_state": "To pay"
  },
  "payers": [],
  "add_credit_card_fee": null,
  "currency_locale": "eur"
}
```

## Example script download all invoices

First we need to get all people in the show via `/meetings/:show_id/people.json` or `/meetings/:show_id/people/zero_balance.json` if you only want zero balanced accounts. When we have all people, loop through each person and get `/meetings/:show_id/people/:person_id/economies.json`.


```ruby
require 'faraday'
require 'json'

# Change this for the show you want to export
SHOW_ID = 0000

# API-key found in app.equipe.com, users, profile for the user
API_KEY = 'YOUR-API-KEY'

response = Faraday.get("https://app.equipe.com/meetings/#{SHOW_ID}/people.json", {}, 'X-API-KEY' => API_KEY)
people = JSON.parse(response.body)

people.each do |person|
  response = Faraday.get("https://app.equipe.com/meetings/#{SHOW_ID}/people/#{person['rnr']}/economies.json", {}, 'X-API-KEY' => API_KEY)
  invoice = JSON.parse(response.body)

  # Print economies for person
  puts invoice.inspect
end
```
