#include <iostream>
#include <fstream>
#include <string>
using namespace std;

class Student {
    string id, name;
    bool present;
public:
    void setData(string i, string n) { id=i; name=n; present=false; }
    void markPresent() { present=true; }
    void display() { cout << id << " " << name << " " << (present?"Present":"Absent") << endl; }
};

void addStudent() {
    Student s;
    string id, name;
    cout << "Enter ID: "; cin >> id;
    cout << "Enter Name: "; cin.ignore(); getline(cin, name);
    s.setData(id, name);
    ofstream file("attendance.txt", ios::app);
    file << id << "," << name << ",Absent\n";
    file.close();
}

void markAttendance() {
    string id;
    cout << "Enter ID to mark present: "; cin >> id;
    // implementation...
}

void viewAttendance() {
    ifstream file("attendance.txt");
    string line;
    while(getline(file, line)) {
        cout << line << endl;
    }
    file.close();
}

int main() {
    int choice;
    do {
        cout << "1. Add Student\n2. Mark Attendance\n3. View Attendance\n4. Exit\n";
        cin >> choice;
        switch(choice) {
            case 1: addStudent(); break;
            case 2: markAttendance(); break;
            case 3: viewAttendance(); break;
        }
    } while(choice != 4);
    return 0;
}
