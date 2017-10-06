# Snippets
Snippets

const _ = require('lodash');

const users = [
  { 'name': 'barney', 'age': 36, 'active': true, 'favouriteFood': 'pizza', 'secondFavouriteFood': 'chips', 'thirdFavouriteFood': 'cheese' },
  { 'name': 'fred', 'age': 40, 'active': false, 'favouriteFood': 'chips and cheese', 'secondFavouriteFood': 'chips' },
  { 'name': 'bambam', 'age': 40, 'active': false, 'favouriteFood': 'pasta', 'secondFavouriteFood': 'cheese' }  
];
 

const filterText = 'cheese';
const filterRegexText = new RegExp(filterText);

const filterColumns = ['favouriteFood', 'secondFavouriteFood'];
const filterQuery = (o) => _.includes(_.toLower(o), _.toLower(filterText));
const filterRegexQuery = (o) => filterRegexText.test(o);

const filteredUsers = _.filter(users, (o) => _.some(_.pick(o, filterColumns), filterRegexQuery ) );

console.log(filteredUsers);
