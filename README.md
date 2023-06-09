# LibraryManage.
the folder 'gb' is the Database used.



-----------------------------------------------------THE APP------------------------------------------------------


The "mainwindow.py" file defines the main window of the application. It creates three buttons: "Login," "Sign Up," and "About." The buttons are connected to slots (functions) that handle their respective actions. The main window also sets a background image and defines its layout.

The signup method is responsible for handling the sign-up logic. It retrieves the entered username and password from the line edits. It then defines a salt value, which is a fixed string used for password hashing. The password is hashed using the hashlib library, specifically the SHA256 algorithm, by concatenating the password with the salt and computing the hash. This ensures that even if two users have the same password, their hashed passwords will be different.

The method then checks if the entered username already exists in the database by executing a SELECT query. If a result is returned, it means the username is already taken, and an error message is displayed using a QMessageBox.

If the username is not found in the database, the method proceeds to insert the new user's details (username, hashed password, and salt) into the database using an INSERT query. The database connection is committed to persist the changes, and a success message is displayed using another QMessageBox. Finally, the sign-up dialog is closed.

The login method handles the login logic. It retrieves the entered username and password from the line edits. It then executes a SELECT query to fetch the user's details from the database based on the entered username. The result is fetched using fetchone().

If a result is obtained, the stored salt and hashed password are retrieved from the result tuple. The stored salt is a fixed value used during password hashing. The method then computes the hash of the entered password using the same salt value and checks if it matches the stored hashed password. If the hashes match, a success message is displayed using a QMessageBox and Proceeds to Open the Library GUI.

If the entered username or password is incorrect, an error message is displayed accordingly. If no result is obtained from the database query, it means the entered username does not exist, and an error message is displayed.

The Library Gui or the main app presents a visually appealing window containing a treeview widget that efficiently displays book records. Users can interact with the system using a set of intuitive buttons. The "Add Book" button launches a user-friendly form for adding new book records, ensuring seamless data entry. Similarly, the "Update Book" button opens a form where existing book records can be easily modified, maintaining data accuracy. The "Delete Book" button provides a convenient way to remove selected book records from the database, promoting efficient data management. Additionally, users can utilize the "Search" button to find books based on title or publication year, enabling quick access to specific information. Furthermore, the "Search By Author" button facilitates book searches based on author, enhancing the search capabilities of the application. Lastly, the "Reset" button renews the displayed book records in the treeview, ensuring real-time updates and a seamless user experience. 
