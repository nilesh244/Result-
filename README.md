#include <iostream>
#include <cstdlib>
#include <ctime>
#include <thread>
#include <chrono>
using namespace std;

void loadingAnimation() {
    for (int i = 0; i < 3; ++i) {
        cout << ".";
        this_thread::sleep_for(chrono::milliseconds(500));
    }
    cout << endl;
}

int main() {
    string name;
    int rollNo;

    cout << "Enter your name: ";
    getline(cin, name);

    cout << "Enter your roll number: ";
    cin >> rollNo;

    cout << "\nFetching result";
    loadingAnimation();
    loadingAnimation();

    srand(time(0));
    int marks[5];
    string subjects[5] = {"Math", "Science", "English", "History", "Computer"};
    int total = 0;

    cout << "\n---- Result for " << name << " ----\n";
    for (int i = 0; i < 5; i++) {
        marks[i] = rand() % 41 + 60; // Random marks between 60-100
        cout << subjects[i] << ": " << marks[i] << "/100\n";
        total += marks[i];
    }

    float percentage = total / 5.0;
    cout << "----------------------------\n";
    cout << "Total: " << total << "/500\n";
    cout << "Percentage: " << percentage << "%\n";

    if (percentage >= 90)
        cout << "Grade: A+ (Genius!)\n";
    else if (percentage >= 75)
        cout << "Grade: A\n";
    else if (percentage >= 60)
        cout << "Grade: B\n";
    else
        cout << "Grade: C (Work Harder!)\n";

    cout << "\n** Prank: This is a fake result! Don't panic! **\n";

    return 0;
}
