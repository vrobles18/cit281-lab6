# cit281-lab6

class Book {
    constructor(given_title, author, pubDate, isbn) {
      this.given_title = title;
      this.author = author;
      this.pubDate = pubDate;
      this.isbn = isbn;
    }
}
 

//Part 5: Create and test Library class
 class Library {
    constructor(name) {
      this._name = name;
      this._books = [];
    }
    get books() {
      // Return copy of books
      return JSON.parse(JSON.stringify(this._books));
    }
    get count() {
      return this._books.length;
    }
    addBook(book = {}) {
      const { title = "", author = "", pubDate = "" } = book;
      if (title.length > 0 && author.length > 0) {
        const newBook = { title, author, pubDate };
        this._books.push(newBook);
      }
    }
    listBooks() {
      for (const book of this._books) {
        const {title, author, pubDate, isbn} = book;
        console.log(`Title: ${title}, Author: ${author}, PubDate: ${pubDate}`)
      }
    }
  }

deleteBook(isbn) {
    for (const book of this._books) {
        if (isbn === book.isbn) {
           console.log("Found book!", book) 
        }
    }
}
}


const uoLibrary = new Library("Knight");

// Create a book, add at least two more
const atomicHabits = new Book("Atomic Habits", "James Clear", "10/16/2018", "1234567890");
const ohThePlacesYoullGo = new Book("Oh, the Places You'll Go!", "Dr.Seuss", "01/22/1990", "0987654");
const greenEggsAndHam = new Book("Green Eggs and Ham","Dr.Seuss", "08/12/1960", "102938");

uoLibrary.addBook(atomicHabits);
uoLibrary.addBook(ohThePlacesYoullGo);

uoLibrary.listBooks();




// Create books
const atomicHabits = new Book("Atomic Habits", "James Clear", "10/16/2018", "0735211299");
const theHillWeClimb = new Book("The Hill We Climb", "David Baldacci", "03/30/2021", "059346527X");
const oceanPrey = new Book("Atomic Habits", "John Sandford", "04/13/2021", "1398505501");

// Add books to library and output library count and books
library.addBook(atomicHabits);
library.addBook(theHillWeClimb);
library.addBook(oceanPrey);
console.log(`Book count: ${library.count}`);
library.listBooks();

// Delete a book and output library books
console.log("* Library after delete *");
library.deleteBook("059346527X");
library.listBooks();
