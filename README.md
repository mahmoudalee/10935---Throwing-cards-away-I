# 10935---Throwing-cards-away-I

#include <iostream>

#include <queue>

using namespace std;

int main()
{

	int n;
	while (cin >> n && n)
	{
		if (n == 1)
			cout << "Discarded cards:\nRemaining card: 1" << endl;
		else
		{
			queue<int>q, remaining;

			for (int i = 0; i < n; i++)
			{
				q.push(i + 1);
			}

			while (q.size() > 1)
			{
				remaining.push(q.front());
				q.pop();
				q.push(q.front());
				q.pop();
			}

			cout << "Discarded cards: " << remaining.front();
			remaining.pop();

			while (!remaining.empty())
			{
				cout << ", " << remaining.front();
				remaining.pop();
			}
			cout << endl << "Remaining card: " << q.front() << endl;
		}
	}
	return 0;
}
