# Database-Connection


import mysql.connector

mydatabase = mysql.connector.connect(
    host="localhost",
    user="username",
    password="password",
    database="mydatabase"
)

mycursor = mydatabase.cursor()

sql_query = "INSERT INTO student (name, address) VALUES (%s, %s)"
value = ("Prachi", "Noida")
mycursor.execute(sql_query, value)

mydatabase.commit()

print(mycursor.rowcount, "record inserted.")
