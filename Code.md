#include <iostream>
using namespace std;

float getGradePoint(char grade) {
    switch(grade) {
        case 'A': return 4.0;
        case 'B': return 3.0;
        case 'C': return 2.0;
        case 'D': return 1.0;
        case 'F': return 0.0;
        default: return 0.0;
    }
}

int main() {
    int n;
    cout << "Enter number of courses: ";
    cin >> n;

    float totalCredits = 0, totalPoints = 0;

    for(int i = 0; i < n; i++) {
        char grade;
        float credit;

        cout << "Enter grade for course " << i+1 << ": ";
        cin >> grade;

        cout << "Enter credit hours: ";
        cin >> credit;

        float gp = getGradePoint(grade);

        totalCredits += credit;
        totalPoints += gp * credit;
    }

    cout << "\nCGPA: " << totalPoints / totalCredits << endl;

    return 0;
}
