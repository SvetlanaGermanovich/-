C++
#include <algorithm>    // std::sort
#include <vector>       // std::vector
#include <iterator>
#include <iostream>
 
using namespace std;
 
int get_digits_sum(int x) {
    if (!x)
        return 0;
    else
        return x % 10 + get_digits_sum(x / 10);
}
 
int func(int a, int b) {
    return get_digits_sum(a) > get_digits_sum(b);
}
 
int main() {
    vector<int> myvector = {12, 43, 56, 32, 112, 5, 77, 8, 999};
    sort(myvector.begin(), myvector.end(), func);
    copy(myvector.begin(), myvector.end(), ostream_iterator<int>(cout, " "));
    return 0;
}
