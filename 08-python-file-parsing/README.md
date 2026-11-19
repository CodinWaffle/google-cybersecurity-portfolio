# Algorithm for File Updates in Python

## Project Description
This project automates access control management for a healthcare organization by updating an IP address allow list (`allow_list.txt`) using Python. When employees change roles or leave the company, their IP addresses are added to a `remove_list`. This algorithm parses the current allow list, cross-references it against the `remove_list`, removes any matching IP addresses, and overwrites the file with the updated list of authorized IPs.

---

## Complete Python Algorithm

```python
def update_file(import_file, remove_list):
    # Open and read the allow list file
    with open(import_file, "r") as file:
        ip_addresses = file.read()

    # Convert the string of IP addresses into a list
    ip_addresses = ip_addresses.split()

    # Iterate through the remove list and delete matching IPs
    for element in remove_list:
        if element in ip_addresses:
            ip_addresses.remove(element)

    # Convert the revised list back into a newline-separated string
    ip_addresses = "\n".join(ip_addresses)

    # Overwrite the original file with the updated allow list
    with open(import_file, "w") as file:
        file.write(ip_addresses)

# Example Usage
import_file = "allow_list.txt"
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

update_file(import_file, remove_list)
