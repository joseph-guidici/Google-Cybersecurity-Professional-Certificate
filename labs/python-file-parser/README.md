# Lab 07 - Update a File Through a Python Algorithm

## Objective
Develop a Python algorithm that automates the maintenance of an IP allow list. The script reads a file containing approved IP addresses, removes any addresses that no longer require access, and rewrites the file with the updated contents.

## Scenario Summary
I am a security analyst at a healthcare company. Part of my job is controlling access to restricted content, in this case a subnetwork containing patient medical records. Access is managed through an allow list of IP addresses stored in a file called `allow_list.txt`. A separate remove list identifies IP addresses that should no longer have access. Rather than editing the file by hand every time access changes, my task was to build a Python algorithm that performs the update automatically.

## Tools & Skills
| Category | Details |
|----------|---------|
| Language | Python 3 |
| Concepts | File handling with `with` statements, string and list methods, `for` loops, conditional logic, user-defined functions |
| Methods used | `.read()`, `.split()`, `.remove()`, `.join()`, `.write()` |
| Security application | Access control, allow list maintenance, automation of repetitive analyst tasks |

## Algorithm Walkthrough
1. Defined a function `update_file()` that accepts two parameters: `import_file` (the allow list file) and `remove_list` (the IP addresses to revoke)
2. Opened the allow list in read mode using a `with` statement and stored the contents in a variable with `.read()`
3. Converted the contents from a single string into a list of individual IP addresses using `.split()`
4. Looped through each element in the list and used a conditional statement to check whether it appears in `remove_list`
5. Removed matching addresses from the list with `.remove()`
6. Converted the updated list back into a string with `.join()` so it could be written to a file
7. Reopened the file in write mode and replaced the original contents with the updated allow list
8. Called the function on `allow_list.txt` with three IP addresses to revoke, then read the file back in and printed it to confirm the update worked

## The Code
The full script is available in this folder: [update_file.py](./update_file.py)

The core of the algorithm:

```python
def update_file(import_file, remove_list):
    with open(import_file, "r") as file:
        ip_addresses = file.read()
    ip_addresses = ip_addresses.split()
    for element in ip_addresses:
        if element in remove_list:
            ip_addresses.remove(element)
    ip_addresses = " ".join(ip_addresses)
    with open(import_file, "w") as file:
        file.write(ip_addresses)
```

## Results
Running the script against `allow_list.txt` with the remove list `["192.168.25.60", "192.168.140.81", "192.168.203.198"]` successfully stripped those three addresses from the file. Printing the updated contents confirmed the revoked IPs were gone while every approved address remained intact. What used to be a manual edit is now a single function call.

## Lessons Learned
This lab showed me how much value even a short script can add to day-to-day security work. Manually editing an allow list is slow and easy to get wrong, and a typo in an access control file is a real security risk. Automating it makes the process repeatable and consistent.

The most interesting technical takeaway was a limitation I learned about `.remove()`. Calling it inside a loop that iterates over the same list can cause elements to be skipped if duplicate values sit next to each other, because removing an item shifts the positions of everything after it. It works for this lab since each IP address in the allow list is unique, but in a production version I would iterate over a copy of the list or use a list comprehension to build a new one. Knowing where an approach breaks down feels just as important as knowing that it works.

Going forward I would like to extend this script to log each removal with a timestamp, which would create an audit trail showing when access was revoked and why.

---

## 🔗 Back to Main Portfolio

[← Return to Google Cybersecurity Certificate Repository](../../README.md)