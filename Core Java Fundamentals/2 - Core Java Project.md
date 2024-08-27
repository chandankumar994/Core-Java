
Let's build a simple console-based "Library Management System" using the concepts learned throughout the course. This project will involve classes, objects, inheritance, collections, file handling, and exception handling.

### **Project: Library Management System**

#### **Project Overview:**
- **Features:**
  1. Add a new book to the library.
  2. Issue a book to a user.
  3. Return a book.
  4. Display all books.
  5. Save and load book data from a file.

#### **Step 1: Define Classes**

- **Book Class:**
  - Represents a book in the library.
  - Contains attributes like title, author, and availability status.
  
- **Library Class:**
  - Manages the collection of books.
  - Provides methods to add, issue, return, and display books.

#### **Book.java**
```java
import java.io.Serializable;

public class Book implements Serializable {
    private String title;
    private String author;
    private boolean isIssued;

    // Constructor
    public Book(String title, String author) {
        this.title = title;
        this.author = author;
        this.isIssued = false;
    }

    // Getters
    public String getTitle() {
        return title;
    }

    public String getAuthor() {
        return author;
    }

    public boolean isIssued() {
        return isIssued;
    }

    // Issue the book
    public void issueBook() {
        if (!isIssued) {
            isIssued = true;
        } else {
            System.out.println("Book is already issued.");
        }
    }

    // Return the book
    public void returnBook() {
        if (isIssued) {
            isIssued = false;
        } else {
            System.out.println("Book was not issued.");
        }
    }

    @Override
    public String toString() {
        return "Title: " + title + ", Author: " + author + ", Issued: " + isIssued;
    }
}
```

#### **Library.java**
```java
import java.util.ArrayList;
import java.util.Scanner;
import java.io.*;

public class Library {
    private ArrayList<Book> books;

    // Constructor
    public Library() {
        books = new ArrayList<>();
    }

    // Add a new book
    public void addBook(Book book) {
        books.add(book);
        System.out.println("Book added successfully!");
    }

    // Issue a book
    public void issueBook(String title) {
        for (Book book : books) {
            if (book.getTitle().equalsIgnoreCase(title)) {
                book.issueBook();
                System.out.println("Book issued successfully!");
                return;
            }
        }
        System.out.println("Book not found.");
    }

    // Return a book
    public void returnBook(String title) {
        for (Book book : books) {
            if (book.getTitle().equalsIgnoreCase(title)) {
                book.returnBook();
                System.out.println("Book returned successfully!");
                return;
            }
        }
        System.out.println("Book not found.");
    }

    // Display all books
    public void displayBooks() {
        if (books.isEmpty()) {
            System.out.println("No books in the library.");
        } else {
            for (Book book : books) {
                System.out.println(book);
            }
        }
    }

    // Save the books to a file
    public void saveBooks() {
        try (ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("books.dat"))) {
            oos.writeObject(books);
            System.out.println("Books saved successfully!");
        } catch (IOException e) {
            System.out.println("Error saving books: " + e.getMessage());
        }
    }

    // Load the books from a file
    public void loadBooks() {
        try (ObjectInputStream ois = new ObjectInputStream(new FileInputStream("books.dat"))) {
            books = (ArrayList<Book>) ois.readObject();
            System.out.println("Books loaded successfully!");
        } catch (IOException | ClassNotFoundException e) {
            System.out.println("Error loading books: " + e.getMessage());
        }
    }
}
```

#### **LibraryManagementSystem.java**
```java
import java.util.Scanner;

public class LibraryManagementSystem {
    public static void main(String[] args) {
        Library library = new Library();
        Scanner scanner = new Scanner(System.in);
        int choice;

        do {
            System.out.println("\nLibrary Management System");
            System.out.println("1. Add Book");
            System.out.println("2. Issue Book");
            System.out.println("3. Return Book");
            System.out.println("4. Display Books");
            System.out.println("5. Save Books");
            System.out.println("6. Load Books");
            System.out.println("7. Exit");
            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            switch (choice) {
                case 1:
                    System.out.print("Enter book title: ");
                    String title = scanner.nextLine();
                    System.out.print("Enter book author: ");
                    String author = scanner.nextLine();
                    library.addBook(new Book(title, author));
                    break;
                case 2:
                    System.out.print("Enter book title to issue: ");
                    title = scanner.nextLine();
                    library.issueBook(title);
                    break;
                case 3:
                    System.out.print("Enter book title to return: ");
                    title = scanner.nextLine();
                    library.returnBook(title);
                    break;
                case 4:
                    library.displayBooks();
                    break;
                case 5:
                    library.saveBooks();
                    break;
                case 6:
                    library.loadBooks();
                    break;
                case 7:
                    System.out.println("Exiting system. Goodbye!");
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        } while (choice != 7);

        scanner.close();
    }
}
```

### **Explanation:**
1. **Book Class:** Represents each book with a title, author, and issue status. It provides methods to issue and return books.

2. **Library Class:** Manages the list of books using an `ArrayList`. It includes methods to add, issue, return, display, save, and load books.

3. **LibraryManagementSystem Class:** The main class to interact with the user. It presents a menu-driven interface to perform various operations.

### **Running the Project:**
- **Compile and run** the `LibraryManagementSystem` class.
- You can interact with the system by selecting the desired option from the menu.

This project helps consolidate your understanding of Core Java by integrating various fundamental concepts into a practical application.
