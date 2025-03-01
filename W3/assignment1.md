## Code


```Java
def main():
    filename = input("Enter name of photo file: ")

    try:
        with open(filename, 'r') as file:
            for line in file:
                photo_filename = line.strip()
                
                if photo_filename:
                    info_filename = photo_filename.replace("_photo.jpg", "_info.txt")
                    print(info_filename)
    except FileNotFoundError:
        print("File not found, please check the file name and try again")

if __name__ == "__main__":
    main()
```
![W3](https://github.com/user-attachments/assets/334d5e7e-3cb3-4647-9ddb-d313d6f4daaf)

A challenge for me was when I was creating a flowchart to cover all the decision points. Handling file I/O gracefully and making sure that the string replacement only affected the filename was hard too
Overall, working through these issues really helped me understand both the design and implementation phases better.
