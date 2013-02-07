#include <iostream>
#include <string>
#include <sstream>
#include <fstream>

using namespace std;

void ascending(string *data, int x)
{
    string temp3;
    for(int y = 0; y < x; y++)
    {
        for(int i = 0; i < x; i++)
        {
            if(data[y] < data[i])
            {
                temp3 = data[y];
                data[y] = data[i];
                data[i] = temp3;
            }
        }
    }

    for(int i = 0; i < x; i++)
    {
        cout << data[i] << endl;
    }
}

void s(string *sorting)
{
    string a = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz";
    int a1 = a.length();
    int b = 0;
    int c = 0;
    for(int j = 0; j < 100; j++)
    {
        int r = sorting[j].length();
        for(int k = 0; k < r; k++)
        {
            if(b == 1)
            {
                b = 0;
                break;
            }

            else if(b == 2)
            {
                c++;
                b = 0;
                break;
            }

            for(int l = 0; l < a1; l++)
            {
                if(sorting[j].at(k) == a.at(l))
                {
                    b = 1;
                    break;
                }

                else if(l == a1 - 1)
                {
                    b = 2;
                    break;
                }
            }
        }
    }


    int sorted[c];
    int x = 0,y;
    string other[100 - c];

    for(int j = 0; j < 100; j++)
    {
        int r = sorting[j].length();
        for(int k = 0; k < r; k++)
        {
            if(b == 1)
            {
                b = 0;
                break;
            }

            else if(b == 2)
            {
                b = 0;
                break;
            }

            for(int l = 0; l < a1; l++)
            {
                if(sorting[j].at(k) == a.at(l))
                {
                    b = 1;
                    break;
                }

                else if(l == a1 - 1)
                {
                    stringstream(sorting[j]) >> y;
                    sorted[x] = y;
                    sorting[j] = "";
                    x++;
                    b = 2;
                    break;
                }
            }
        }
    }

    int xk;
    for(int index = 0; index < c; index++)
    {

        for(int i = 0; i < c; i++)
        {
            if(sorted[i] > sorted[i+1])
            {
                xk = sorted[i];
                sorted[i] = sorted[i+1];
                sorted[i+1] = xk;
            }
        }
    }

    for(int ll = 0; ll < c; ll++)
    {
        cout << sorted[ll] << endl;
    }
    int index = 0;
    for(int j = 0; j < 100; j++)
    {
        int r = sorting[j].length();
        for(int k = 0; k < r; k++)
        {
            if(b == 1)
            {
                b = 0;
                break;
            }
            for(int l = 0; l < a1; l++)
            {
                if(sorting[j].at(k) == a.at(l))
                {
                    other[index] = sorting[j];
                    b = 1;
                    index++;
                    break;
                }
            }
        }
    }

    ascending(other, 100 - c);

}

int main()
{
    ifstream ReadFile;
    fstream BothRW;
    string line;
    string sort[100];
    int i = 0;
    ReadFile.open("top_passwords.txt");
    while(ReadFile.good())
    {
        getline(ReadFile, line);
        sort[i] = line;
        i++;
    }

    s(sort);
    ReadFile.close();
    return 0;
}
