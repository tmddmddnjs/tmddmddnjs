#include <string>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;

vector<string> solution(int n, vector<int> arr1, vector<int> arr2) {
	vector<string> answer;
	vector<string> arr_string;
	//arr1,2의 값들을 2진수로 변환
	for (int i = 0; i < n; i++) {
		for (int j = 0; j < n; j++) {
			if (arr1[i] % 2 == 1)
				arr_string.push_back("#");
			else if (arr2[i] % 2 == 1)
				arr_string.push_back("#");
			else
				arr_string.push_back(" ");
			arr1[i] /= 2;
			arr2[i] /= 2;

		}
		//공백과 #을 역순으로 해서 answer에 넣는다.
		reverse(arr_string.begin(), arr_string.end());
		for (int k = 0; k < arr_string.size(); k++) {
			answer.push_back(arr_string[k]);
		}
		//비우고 새로 입력받음
		arr_string.clear();

		//공백과 #을 역순으로 해서 answer에 넣는다.
		/*answer.push_back(arr_string[n - 1]);
		for (int j = n - 2; j >= 0; j--) {
			answer[i] += arr_string[j];
		}
		arr_string.clear();*/
	}
	for (int i = 0; i < answer.size(); i++) {
		cout << answer[i];
		if ((i + 1) % n == 0)cout << endl;
	}
	cout << endl << endl;
	return answer;
}

int main() {
	int n = 5;
	vector<int> arr1 = { 9, 20, 28, 18, 11 };
	vector<int> arr2 = { 30, 1, 21, 17, 28 };
	solution(n, arr1, arr2);

	int n2 = 6;
	vector<int> arr11 = { 46, 33, 33 ,22, 31, 50 };
	vector<int> arr22 = { 27 ,56, 19, 14, 14, 10 };
	solution(n2, arr11, arr22);
}