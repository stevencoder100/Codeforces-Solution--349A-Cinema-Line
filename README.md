#include<iostream>

using namespace std;

int main()
{
    int n;
    
    ios_base::sync_with_stdio(false);
    cin.tie(0);
    cout.tie(0);
    
    cin >> n;
    
    int twenty_five = 0, fifty = 0;
    
    int money;
    
    while(n--)
    {
        cin >> money;
        
        if(money == 25)
        {
            ++twenty_five;
        }
        
        else if(money == 50)
        {
            if(twenty_five > 0)
            {
                ++fifty;
                --twenty_five;
            }
            else
            {
                cout << "NO";
                return 0;
            }
       }
       else if(money == 100)
       {
            if(twenty_five == 0)
            {
                cout << "NO";
                return 0;
            }
            else if(fifty > 0)
            {
                --fifty;
                --twenty_five;
            }
            else if(fifty == 0)
            {
                if(twenty_five >= 3)
                {
                    twenty_five -= 3;
                }
                else
                {
                    cout << "NO";
                    return 0;
                }
            }
       }
    }
    
    cout << "YES";
    return 0;
}