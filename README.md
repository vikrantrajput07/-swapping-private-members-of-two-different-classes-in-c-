// swapping private members of two different classes
#include<iostream>
using namespace std;
class t;
class s
{
private:
  int a = 20, b = 30;
public:
    friend void swap (s, t);

};
class t
{
private:
  int x = 1, y = 2;
public:
    friend void swap (s, t);
};

void
swap (s q, t p)
{
  int c, d;
  c = q.a;
  q.a = p.x;
  p.x = c;
  d = q.b;
  q.b = p.y;
  p.y = d;

  cout << q.a << "," << q.b << endl;
  cout << p.x << "," << p.y<<endl;
}

int
main ()
{
  s s1;
  t t1;
  swap (s1, t1);
}
