# EdYoda_Project
import json

class Employee:
    def __init__(self, name, dob, height, city, state):
        self.name = name
        self.dob = dob
        self.height = height
        self.city = city
        self.state = state

def read_employee_json(file_path):
    
    try:
        # Open the JSON file
        with open(file_path, 'r') as f:
            # Load the JSON data
            data = json.load(f)
            
            # Create a list to store the Employee objects
            employees = []
            
            # Loop through the data and create Employee objects
            for employee_data in data:
                employee = Employee(employee_data['Name'], employee_data['DOB'], employee_data['Height'], employee_data['City'], employee_data['State'])
                employees.append(employee)
            
            # Return the list of Employee objects
            return employees()           
   
    except FileNotFoundError:
        # Log the error
        print("Error: File not found")
        return []
# Example usage
employees = read_employee_json('employee.json')
for employee in employees:
    print(employee.__dict__)
