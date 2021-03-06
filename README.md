# Courier Kata

## Approach

The brief mentions that the library should be programmatic. I interpreted that to be that the library should manage the business logic of calculating the cost of sending a parcel order. Therefore, my decisions don't currently address the interface / transport layer of the application.

## Prices

As the brief doesn't explicitly mention the currency, and in order to keep the library currency agnostic to be able to keep the library scalable and reuseable, prices are stored as integers (in pennies, or the lowest unit of currency). This also avoids floating point errors. A helper method can be used to convert the integer into a string for presentation purposes.

Also, as the prices might be subject to change, I've separated it out into its own file.

## Functional programming Vs Object oriented programming

I've recently been investigating the functional approach Vs the object oriented approach. My previous experience at Makers has been very much object oriented, and I'm very familiar with that. However, for this project I wanted to try out a more functional approach where my library to keep my library more stateless and have discrete functional units which can be brought together to do a task.

To keep the library truly stateless, I would like to move the parcel prices out of the application into a persistence database layer. However, given the time constraint I haven't implemented this here.

## Privacy

In order to keep the implementation private, I'm using the revealing module pattern offered by javascript to take advantage of closures to 'hide' the implementation details from the public.

More about revealing module pattern [here](https://github.com/getify/You-Dont-Know-JS/blob/master/scope%20%26%20closures/ch5.md)

## Testing

Coming soon.

## Linting

This project uses ESlint along with Prettier. I'm using a modified version of Wes Bos' 'No Sweat' ESlint and prettier setup that uses the airbnb eslint config which is well regarded by the wider JS community.

## Git strategy

I've followed the Atomic commit message strategy to keep my commits to one feature, fix or improvement.

I'm following the [semantic commit message strategy](https://www.conventionalcommits.org/en/v1.0.0-beta.2/#specification) to make my commits scannable and easy to parse.

## Branching Strategy

I worked on the master branch to create a working hello world react app that loads mock product data (supplied in the requirements) into the application state (App.state.products).

Following that, all work is carried out on the dev branch, and every feature was developed on its own branch followed by a pull request to merge into dev and subsequently into master. Once merged, branches are deleted.
