# Create an empty dictionary to store patient records

patient_records = {}  # Main dictionary to hold all patient data

# Define the insert function

def insert(record_number, first_name, last_name, vaccines):

    """
    Adds a new patient record to the patient_records dictionary.

    record_number: unique string for the patient, e.g., 'R001'
    first_name: patient's first name
    last_name: patient's last name
    vaccines: dictionary of vaccines with scheduled months
    """
    # Add the patient details under the given record number
    patient_records[record_number] = {
        "First Name": first_name,
        "Last Name": last_name,
        "Vaccines": vaccines
    }
    print(f"Patient {first_name} {last_name} added with record {record_number}.")


# Add sample patient records

# Patient 1: John Smith
john_vaccines = {
    "HepB": [0, 1, 6],
    "RV": [2, 4, 6],
    "DTaP": [2, 4, 6, 15],
    "Hib": [2, 4, 6, 12],
    "PCV13": [2, 4, 6, 12],
    "IPV": [2, 4, 6],
    "IIV4": ["Annual"],
    "MMR": [12],
    "VAR": [12],
    "HepA": [12]
}
insert("R001", "John", "Smith", john_vaccines)

# Patient 2: Olivia James
olivia_vaccines = {
    "HepB": [0, 1, 6],
    "RV": [2, 4, 7],
    "DTaP": [2, 5, 7, 12],
    "Hib": [2, 4, 6, 12],
    "PCV13": [2, 5, 7, 12],
    "IPV": [2, 5, 8],
    "IIV4": ["Annual"],
    "MMR": [12],
    "VAR": [12],
    "HepA": [12]
}
insert("R002", "Olivia", "James", olivia_vaccines)


# Verify the patient records

print("\nAll patient records:")
for rec_num, details in patient_records.items():
    print(f"\nRecord Number: {rec_num}")
    print(f"Patient Name: {details['First Name']} {details['Last Name']}")
    print("Vaccines and Months:")
    for vaccine, months in details["Vaccines"].items():
        print(f"  {vaccine}: {months}")


# Notes

# - Each patient has a unique record number (R001, R002, etc.)
# - Vaccines are stored as nested dictionaries for clarity
# - You can call insert() multiple times to add more patients without overwriting existing records
# - Easy to expand with more vaccines or patients in the future
