# Restaurant_GraphQL
Query data from a JSON file using GraphQL

## Description
This is a basic application that uses GraphQL to setup a restaurant schema. By navigating the port 5500/graphQL, the graph QL interface displays on the browser and you can query different parts of the restaurant data located in the restaurants.json file.

## How to Run
Clone Restaurant_GraphQL to your local computer. First run an NPM Install to aquire necessary packages. Next run a node index.js. Finally navigate to localhost port specified /graphql

## Here are the query and mutation structures
query getContacts{
contacts{
name
email
}
query getContact($iid: Int = 1){
    contact(id:$id){
name
email
}
}

mutation setContacts{
setContact(input: {
name: "john williams",
email: "jrw@mit.edu",
age:50
}){
name
email
age
}
}

query getContacts{
contacts{
name
email
}
}
mutation deleteContacts($idd: Int = 1){
  deleteContact(id: $idd){
ok
}
}

mutation editContacts($idd: Int = 1, $age: Int = 35){
editContact(id: $idd, age: $age){
name
age
}
}

mutation editrestaurants($idd: Int = 1, $name: String = "OLDO"){
editrestaurant(id: $idd, name: $name){
name
description
}
}
mutation setrestaurants {
setrestaurant(input: {
name: "Granite",
description: "American"}) {
name
description
}
}
mutation deleterestaurants($idd: Int = 1){
  deleterestaurant(id: $idd){
ok
}
}
query getrestaurants {
restaurants {
name
description
dishes{
name
price
}
}
}
query getrestaurant($iid: Int = 1){
    restaurant(id:$iid){
name
description
}
}

## License
MIT License

Copyright (c) 2021 Sam Clark

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
