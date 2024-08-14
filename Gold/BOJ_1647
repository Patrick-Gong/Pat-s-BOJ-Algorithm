#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int parent[100001];

int getParent(int x) {
	if (parent[x] == x) return x;
	else return parent[x] = getParent(parent[x]);
}

bool sameParent(int x, int y) {
	return getParent(x) == getParent(y);
}

void Union(int a, int b) {
	a = getParent(a);
	b = getParent(b);

	if (a < b) parent[b] = a;
	else parent[a] = b;
}

int main() {
	int houses, routes, sum=0;
	vector<pair<int, pair<int, int>>> input;
	vector<int> result;

	cin >> houses >> routes;

	for (int j = 1; j <= houses; j++) {
		parent[j] = j;
	}

	for (int i = 0; i < routes; i++) {
		int a, b, c;
		cin >> a >> b >> c;
		input.push_back({ c, {a, b} });
		
	}

	sort(input.begin(), input.end());

	for (int k = 0; k < input.size(); k++) {
		int cost = input[k].first;
		int a = input[k].second.first;
		int b = input[k].second.second;

		if (!sameParent(a, b)) {
			Union(a, b);
			result.push_back(cost);
		}
	}

	for (int p = 0; p < result.size()-1; p++) {
		sum += result[p];
	}
	cout << sum;

	
	return 0;
}
