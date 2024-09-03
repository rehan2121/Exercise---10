###📚 Library Management System

Welcome to the Library Management System! This program helps you manage your collection of books, allowing you to add, view, update, delete, and find books easily.

Features

➕ Add a new book to the library
👀 View all books in the library
✏️ Update details of an existing book
❌ Delete a book from the library
🔍 Find a book by its name and author
Getting Started

To use this program, simply run the Python script. You will be presented with a menu to choose from various options to manage your library.

Prerequisites
Make sure you have Python installed on your system. This program is compatible with Python 3.

How to Run
Save the script to a file, for example, library_management.py.
Open a terminal or command prompt.
Navigate to the directory where you saved the file.
Run the script using the command:
sh
Copy code
python library_management.py
Usage

When you run the program, you will see a menu like this:

markdown
Copy code
                Library Management System

                1. Add Book
                2. View Book
                3. Update Book
                4. Delete Book
                5. Find Book
                6. Exit Programme
Adding a Book
To add a book, select option 1 and follow the prompts to enter the book's details.

python
Copy code
def add_book():
    book = input("\nEnter The Book Name : ")
    author = input("Enter The Author Name : ")
    page = int(input("Enter The Total Pages : "))
    reviews = int(input("Enter The Rating (Out Of 10) : "))
    if reviews > 10:
        print("Please Give A Proper Rating (Out Of 10)")
        return
    category = input("Enter The Category Of Book : ")

    book_details = {
        "Book": book,
        "Author": author,
        "Pages": page,
        "Review": reviews,
        "Category": category
    }

    Books.append(book_details)
    print("Book Is Added!\n", Books, "\n")
Viewing Books
To view all books, select option 2. The program will display a list of all books in the library.

python
Copy code
def view_book():
    if not Books:
        print("Please Add The Book First")
    else:
        for index, book in enumerate(Books, start=1):
            print(f"{index} \n {book}")
Updating a Book
To update a book, select option 3. You will be prompted to choose a book to update and enter the new details.

python
Copy code
def update_book():
    if not Books:
        print("Please Add The Book First")
    else:
        for index, book in enumerate(Books, start=1):
            print(f"\n{index}. {book}")
        
        update = int(input("Enter The Number Of Book to Update : ")) - 1
        if update < 0 or update >= len(Books):
            print("This Is An Invalid Number")
            return
        
        print("Please Fill The Details Given Below: ")

        new_book_name = input("Enter The Book Name : ")
        new_author_name = input("Enter The Author Name : ")
        new_pages = int(input("Enter The Total Pages : "))
        new_reviews = int(input("Enter The Rating (Out Of 10) : ")) 
        if (new_reviews > 10):
            print("Please Give A Proper Rating (Out Of 10)")
            return
        new_category = input("Enter The Category Of Book: ")

        Books[update].update({
            "Book": new_book_name,
            "Author": new_author_name,
            "Pages": new_pages,
            "Review": new_reviews,
            "Category": new_category
        })

        print("Book Is Updated!\n", Books, "\n")
Deleting a Book
To delete a book, select option 4. You will be prompted to choose a book to delete.

python
Copy code
def delete_book():
    if not Books:
        print("Please Add The Book First")
    else:
        for index, book in enumerate(Books, start=1):
            print(f"{index}. {book}")
        
        delete = int(input("Enter The Book Number To Delete : ")) - 1
        if (delete < 0 or delete >= len(Books)):
            print("Invalid Book Number\n")
            return
        deleting = Books.pop(delete)
        print(f"The Book Is Deleted: {deleting}")
Finding a Book
To find a book, select option 5 and enter the book's name and author.

python
Copy code
def find_book():
    title_of_book = input("\nEnter The Name Of Book : ")
    author = input("Enter The Author Name : ")

    found = False
    for book in Books:
        if book["Book"] == title_of_book and book["Author"].lower() == author.lower():
            found = True
            print("Book Found: ", book)
            break

    if not found:
        print("The Book Isn't Found\n")
License

This project is licensed under the MIT License.
