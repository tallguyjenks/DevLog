# The C Math Library
	- ## Other Functions
		- ### fabs()
		  id:: 6100e7b4-3478-44b6-86a3-6eef3795a00a
			-
			  ```c++
			  double bodyTemp = 0.0;
			  
			  cout << "Enter body temperature in Fahrenheit: ";
			  cin >> bodyTemp;
			  
			  if (fabs(bodyTemp - 98.6) < 0.0001) {
			  cout << "Temperature is exactly normal." << endl;
			  } else if (bodyTemp > 98.6) {
			  cout << "Temperature is above normal." << endl;
			  } else {
			  cout << "Temperature is below normal." << endl;
			  }
			  ```