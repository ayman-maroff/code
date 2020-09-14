# code
This code shows all incremental strings consisting of x number the user enters and those strings from 1 to a number that the user can enter as well.











void fun4(int n, int kk)
{
	if (kk <= n && kk != 0 && n != 0) {  //condition to do function
		cout << "the resuls is : \n";
		int i, j, z, t, x = 0, sum = 0, a[9999];

		for (i = 0; i < n; i++)           //insert elements inside matrix
			a[i] = i + 1;


		int  s = 0, k, b[9999], c[9999];
		for (j = 0; j < 9999; j++)             //9999 for give all possible expectations
		{
			sum = 0;
			s = 0;
			for (i = 0; i < kk; i++)            //for give 4 value from matrix in evry time
			{
				b[i] = a[rand() % n];              //random
			}
			for (i = 0; i < kk; i++) {            //this two for and s  for delete any matrix has same elements

				for (k = 0; k < kk; k++)
				{
					if (b[k] == b[i])
						s++;

				}
				if (s == 1 || s == 0)                   //the condition for last two for
					s = 0;
				else break;

			}


			if (s == 0)    //this condition means all of elements in matrix are different
			{
				for (i = 0; i < kk; i++)  //this for sorting elements exponentially
				{
					for (k = 0; k < kk; k++)
						if ((b[i]) < (b[k]))
						{
							z = b[i];
							b[i] = b[k];
							b[k] = z;
						}

				}
				t = 1;
				for (i = 0; i < kk; i++)  //for make elements of every matrix as a number
				{
					sum = sum + b[i] * t;
					t = t * 10;

				}
				c[x] = sum;            //save the number in other matrix
				x++;
			}



		}
		for (i = 0; i < x; i++)      ////this for sorting elements exponentially
		{
			for (k = 0; k < x; k++)
				if ((c[i]) < (c[k]))
				{
					z = c[i];
					c[i] = c[k];
					c[k] = z;
				}

		}


		j = 0;
		for (int i = 0; i < x - 1; i++)   //this  (for) for delete the same number and save one copy
			if (c[i] != c[i + 1])
				c[j++] = c[i];

		c[j++] = c[x - 1];

		for (i = 0; i < j; i++) //for display all chains
		{

			while (c[i] != 0)
			{
				cout << c[i] % 10 << " ";
				c[i] = c[i] / 10;
			}
			cout << endl;
		}

	}
	else cout << "false try again with other value\n";

}
