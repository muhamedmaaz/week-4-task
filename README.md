# week-4-task
#include<iostream>
#include<cstring>
using namespace std;

class Program
{
	public:
		int s;
			
		Program(){
			char cnic[] = "XY210351533";	// Last Digit of my CNIC is 3
			int n = strlen(cnic);
			s = int(cnic[n-1]-'0');
		}			
};

class hexagon : public Program{
	double Area, Perimeter, Angle;
	
	public:
		void calcArea(){
			Area = 1.5 * 1.732 * s;
		}
		void calcPeri(){
			Perimeter = 6*s;
		}
		void calcAngleSum(){
			int a = 120;
			Angle = 6 * (a*a);
		}
		void display(){
			cout<<"Area of Hexagon is: "<<Area<<endl;
			cout<<"Perimeter of Hexagon is: "<<Perimeter<<endl;
			cout<<"Sum of all the angles of Hexagon is: "<<Angle<<endl;
		}
		
};

class circle : public Program{
	private:
		int length = s + 1;
		double Area, Perimeter;
	
	public:
		void calcAreaSquare(){
			Area = length * length;
		}
		void calcPeriSquare(){
			Perimeter = 4 * length;
		}
		void display(){
			cout<<"Area of Circle is: "<<Area<<endl;
			cout<<"Perimeter of Circle is: "<<Perimeter<<endl;
		}
		
};

int main()
{
	char ch;
	cout<<"Enter 1 to calculate area, perimeter, and sum of angles of hexagon"<<endl;
	cout<<"Enter 2 to calculate area and perimeter of circle"<<endl;
	cout<<"Press any other key to exit"<<endl;
	cin>>ch;
	
	hexagon hobj;
	circle cobj;
	switch(ch)
	{
		case '1':
			hobj.calcArea();
			hobj.calcPeri();	
			hobj.calcAngleSum();
			hobj.display();
			break;
			
		case '2':
			cobj.calcAreaSquare();
			cobj.calcPeriSquare();
			cobj.display();
			break;
	}
	
	
	
	return false;
}
