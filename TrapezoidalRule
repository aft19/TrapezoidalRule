#include<iostream>
#include<cmath>
#include<string.h>
#define _USE_MATH_DEFINES


using namespace std;


class DELTA_X {
public:
	float calc_delta_x(float low_lim, float upp_lim, float n) {
		return (upp_lim - low_lim) / n;
	}
};

class F_OF_X {
public:
	float f(float x) {
		//return pow(2,x);                                            
		//(2*pow(2.7182,x))+ (2*x*x)+(5*x)+(1)
		return (3*sin(2*x)+1);              //  <------------------------------------------------------- ENTER FUNCTION HERE!
	}
};



class Integral_Calc :  private DELTA_X, private F_OF_X {

private:

	float lowerlim, upperlim, division, x_delta;

public:

	double sum = 0;
	double y_value[100000];

	void getDelta_x() { // enter the data for upp_lim, low_lim and n as parameters
		cout << "Lower Limit of function:" << endl;
		cin >> lowerlim;
		cout << "Upper limit of funtion:" << endl;
		cin >> upperlim;
		cout << "Enter the Number of trapezoids you want to have:" << endl;
		cin >> division;
	
	}


	float calc_delta_x() {
		x_delta = DELTA_X::calc_delta_x(lowerlim, upperlim, division);
		return x_delta;
	}


	float final_calc(float delta_x, float low_lim, float upp_lim, float n) {

		/*for (float i = 0; i <= n; i + delta_x) {
			y_value[(i / (delta_x)) + c] = f(i);
			sum = sum + ((y_value[(i / delta_x) + 1] + y_value[((i / delta_x) + 1) + delta_x]) / 2) * (delta_x);
		}*/
		for (int i =1; i <= (delta_x + (upp_lim - low_lim)) / delta_x; i++) {
			//float c = (-0.1225 * delta_x)-(0.08775*i) + 1;
			//y_value[i] = Function::f((i*delta_x) + c);
			y_value[i] = F_OF_X::f(low_lim + (i - 1) * delta_x);

			
		}
		for (int j =1; j <= n; j++) {
			sum = sum + ((y_value[j] + y_value[j+1]) / 2) * (delta_x);
		}

		/* for (float j = n; j >= 0; j - delta_x) {
		sum = sum+((y_value[j] + y_value[j-delta_x]) / 2)* (delta_x);

		} */

		return sum;
	}

	

	double definite_integral() {
		return Integral_Calc::final_calc(x_delta, lowerlim, upperlim, division);
	}


};

int main() {
	Integral_Calc area;
	area.getDelta_x();
	area.calc_delta_x();


	cout << "Delta_x = : " << area.calc_delta_x() << endl;
	cout << "Area under curve = : " << area.definite_integral() << endl;
	
	
return 0;
}
