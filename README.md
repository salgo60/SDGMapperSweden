# SDGMapper Sweden
* see also [sdg-translations](https://github.com/open-sdg/sdg-translations)

Test to see if we can use [SDGmapper](https://knowsdgs.jrc.ec.europa.eu/sdgmapper) on Swedish Parliament documents to "classify" documents according to [SDG](https://www.undp.org/sustainable-development-goals) see also  [#5 if the Swedish PM can use it and classify documents produced regarding to SDG](https://github.com/salgo60/SDGMapperSweden/issues/5)

Result of this POC
* there is a document size problem [#4](https://github.com/salgo60/SDGMapperSweden/issues/4)
* the API dont use Linked data [#6](https://github.com/salgo60/SDGMapperSweden/issues/6#issuecomment-1163200515) and right now its not planned
* Quality of mapping needs to be investigated, looks like [english is preffered language](https://github.com/salgo60/SDGMapperSweden/issues/6#issuecomment-1163200515)

## Test API
* [Notebook test SFS](https://github.com/salgo60/SDGMapperSweden/blob/main/Notebook/Swedish%20PM%20document%20SFS.ipynb)
* [Notebook test SOU](https://github.com/salgo60/SDGMapperSweden/blob/main/Notebook/SDGMapper%20Swedish%20PM%20document%20SOU.ipynb)
  * looks we have a config problem see [#4](https://github.com/salgo60/SDGMapperSweden/issues/4)

Document:  http://data.riksdagen.se/dokument/sfs-2021-1106.json
* [Lag (2021:1106) om skatteavtal mellan Sverige och Slovenien](https://www.riksdagen.se/sv/dokument-lagar/dokument/_sfs-2021-1106)


Returns 
```
{'data': 
    ['{
      "name": "sdgs", 
      "children": 
        [
          {
             "name": "SDG 1", 
             "n_occurrences": 2, 
             "children": 
                [
                  {
                    "n_occurrences": 1, 
                    "name": "Target 1.3"},
                  {
                     "n_occurrences": 1, 
                     "name": "Target 1.4"}
                 ] }, 
           {
             "name": "SDG 4", 
             "n_occurrences": 3, 
             "children": 
                [
                  {
                    "n_occurrences": 1, 
                     "name": "Target 4.b"}, 
                  {
                    "n_occurrences": 2, 
                    "name": "SDG 4_undetected_target"}
                    ]}, 
            {
              "name": "SDG 9", 
              "n_occurrences": 1, 
              "children": 
                [
                  {
                    "n_occurrences": 1, 
                    "name": "Target 9.5"}
                 ]}, 
            {
              "name": "SDG 10", 
              "n_occurrences": 1, 
              "children": 
                [
                  {
                    "n_occurrences": 1, 
                    "name": "Target 10.1"}
                   ]}, 
            {
              "name": "SDG 15", 
              "n_occurrences": 2, 
              "children": 
                [
                  {
                    "n_occurrences": 2, 
                    "name": "Target 15.2"}
                    ]}, 
            {
              "name": "SDG 16", 
              "n_occurrences": 1, 
              "children": 
                [
                  {
                    "n_occurrences": 1, 
                    "name": "Target 16.10"}
                    ]}, 
             {
              "name": "SDG 17", 
              "n_occurrences": 2, 
              "children": 
                [
                  {
                    "n_occurrences": 2, 
                    "name": "Target 17.1"}
                    ]}
           ], 
           "api version": "v1"}'
        ]
      }
```
Using the web tool this can be visualized as

![
](https://blogger.googleusercontent.com/img/a/AVvXsEifgKYZNw96LBE23n2ie5af64Tq0Y0A5W65QjFrs14UEqXyT6exPeMbMlUWHMPCuQNAqFERxLmd1jWhAh7Acy5FJr3Y8DcJCGkeSiza1eQUVxC6eTZ0rz8_eOzGoX74sAQYCRWAdjaf9P0nChhl9sHVxDfZluBKaQfai0DQD0eG9rFGfqaBviBZGpPl4g=w537-h483)

![
](https://blogger.googleusercontent.com/img/a/AVvXsEgL2rhYGoZVF3W4Rng-S36FZ-8IPLWwP_J5hanCEKYjOz9rJrBVrDajfQw2jx4CFEMzhEZly2uR0k_5yVLnPjyrCZTAMUSs-R1_cRQVQWgOQeVYV5BLZWvqkdRq0w06ir3vFRrqqTJExKt2pdrz1T_cIvQuJSlat1RGxL25MmsfiWf0PwDeyFsa_uLNzg=w611-h327)


![](https://github.com/salgo60/SDGMapperSweden/blob/main/img/sdg-indicators-table_lag1.png?raw=true)

## Test web tool
Small tests done with the web interface
* document "[SOU 2022:33 Om prövning och omprövning – en del av den gröna omställningen](https://data.riksdagen.se/fil/9E651472-8B12-44BF-9E28-0579589E3DD8) 2022-06-14"
<img src=https://community.dataportal.se/assets/uploads/files/1655298199431-5099930a-70a3-4b41-8206-dc492dd76830-image.png width=500>
<img src="https://community.dataportal.se/assets/uploads/files/1655299309177-165f3fcb-25a5-4ffd-9366-c7a53fcb9c7e-image.png" width=500>
<img src="https://community.dataportal.se/assets/uploads/files/1655299391609-82a3c4fa-8519-4b68-bedb-af0858e2b5a0-image.png" width=500>

* document "[Vår demokrati - värd att värna varje dag - Statens offentliga utredningar 2022:28](https://data.riksdagen.se/fil/8A0EDDF0-A1CF-4A63-91AA-99E06B41DE13)"
<img src="https://community.dataportal.se/assets/uploads/files/1655298787306-00850587-0fbe-4367-b819-f1e12aea6400-image-resized.png" width=500>

<img src="https://github.com/salgo60/SDGMapperSweden/blob/main/img/sdg-indicators-table_dem1.png?raw=true" width=500/>
