# Hospital-Management-System
Objective: To create a simple command-line-based hospital management system to handle patient records, doctor information, and appointments.
#hospital management system

class Patient:
    def __init__(self, patient_id, name, age, gender):
        self.patient_id = patient_id
        self.name = name
        self.age = age
        self.gender = gender

    def __str__(self):
        return f"ID: {self.patient_id}, Name: {self.name}, Age: {self.age}, Gender: {self.gender}"


class Doctor:
    def __init__(self, doctor_id, name, specialty):
        self.doctor_id = doctor_id
        self.name = name
        self.specialty = specialty

    def __str__(self):
        return f"ID: {self.doctor_id}, Name: {self.name}, Specialty: {self.specialty}"


class Appointment:
    def __init__(self, appointment_id, patient_id, doctor_id, date, time):
        self.appointment_id = appointment_id
        self.patient_id = patient_id
        self.doctor_id = doctor_id
        self.date = date
        self.time = time

    def __str__(self):
        return f"ID: {self.appointment_id}, Patient ID: {self.patient_id}, Doctor ID: {self.doctor_id}, Date: {self.date}, Time: {self.time}"


class Hospital:
    def __init__(self):
        self.patients = []
        self.doctors = []
        self.appointments = []

    def add_patient(self):
        patient_id = input("Enter patient ID: ")
        name = input("Enter patient name: ")
        age = input("Enter patient age: ")
        gender = input("Enter patient gender: ")
        self.patients.append(Patient(patient_id, name, age, gender))
        print("Patient added successfully!")

    def view_patients(self):
      if not self.patients:
        print("No patients in the system.")
        return
      for patient in self.patients:
          print(patient)

    def add_doctor(self):
        doctor_id = input("Enter doctor ID: ")
        name = input("Enter doctor name: ")
        specialty = input("Enter doctor specialty: ")
        self.doctors.append(Doctor(doctor_id, name, specialty))
        print("Doctor added successfully!")

    def view_doctors(self):
      if not self.doctors:
        print("No doctors in the system.")
        return
      for doctor in self.doctors:
          print(doctor)

    def add_appointment(self):
        appointment_id = input("Enter appointment ID: ")
        patient_id = input("Enter patient ID: ")
        doctor_id = input("Enter doctor ID: ")
        date = input("Enter appointment date: ")
        time = input("Enter appointment time: ")
        self.appointments.append(Appointment(appointment_id, patient_id, doctor_id, date, time))
        print("Appointment added successfully!")

    def view_appointment(self):
      if not self.appointments:
        print("No appointment in the system.")
        return
      for appointment in self.appointments:
          print(appointment)

if __name__ == "__main__":
    hospital = Hospital()

    while True:
        print("\nHospital Management System")
        print("1. Patient Management")
        print("2. Doctor Management")
        print("3. Appointment Management")
        print("4. Exit")
        choice = input("Enter your choice: ")

        if choice == "1":
          print("\nPatient Management")
          print("1. Add Patient")
          print("2. View all patient details")

          patient_choice = input("Enter choice:")
          if patient_choice == "1":
            hospital.add_patient()
          elif patient_choice == "2":
            hospital.view_patients()

        elif choice == "2":
            print("\ndoctor Management")
            print("1. Add doctor")
            print("2. View all doctor details")

            doctor_choice = input("Enter choice:")
            if doctor_choice == "1":
              hospital.add_doctor()
            elif doctor_choice == "2":
              hospital.view_doctors()

        elif choice == "3":
              print("\nappointment Management")
              print("1. Add appointment")
              print("2. View all appointment details")

              appointment_choice = input("Enter choice:")
              if appointment_choice == "1":
                hospital.add_appointment()
              elif appointment_choice == "2":
                hospital.view_appointment()

        elif choice == "4":
              print("Exiting...")
              break
        else:
              print("Invalid choice. Please try again.")
