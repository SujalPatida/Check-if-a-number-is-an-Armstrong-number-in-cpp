#include <iostream>
#include <cmath>   // for pow() function
using namespace std;

Int main() {
    int num, original, remainder, n = 0;
    double result = 0.0;

    cout << "Enter an integer: ";
    cin >> num;

    original = num;

    // Count number of digits
    while (original != 0) {
        original /= 10;
        ++n;
    }

    original = num;  // reset original number

    // Compute sum of nth power of digits
    while (original != 0) {
        remainder = original % 10;
        result += pow(remainder, n);
        original /= 10;
    }

    // Check Armstrong condition
    if ((int)result == num)
        cout << num << " is an Armstrong number." << endl;
    else
        cout << num << " is NOT an Armstrong number." << endl;

    return 0;
}
