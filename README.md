#       
        int[,] myArr = new int[7,7];
        int[] ochered = new int[7];
		bool[] vis = new bool[7];
        for (int i = 0; i<7; i++)
        {
            for (int j = 0; j<7; j++)
            {
                myArr[i, j] = 0;
                myArr[0, 1] = 1;
                myArr[0, 2] = 1;
                myArr[0, 6] = 1;
                myArr[1, 0] = 1;
                myArr[1, 2] = 1;
                myArr[1, 3] = 1;
                myArr[2, 0] = 1;
                myArr[2, 1] = 1;
                myArr[3, 4] = 1;
                myArr[3, 1] = 1;
                myArr[4, 5] = 1;
                myArr[4, 3] = 1;
                myArr[5, 6] = 1;
                myArr[5, 4] = 1;
                myArr[6, 5] = 1;
                myArr[6, 0] = 1;
                Console.Write("{0}\t", myArr[i,j]);
            }
            Console.WriteLine();
        }
        Console.WriteLine();
    
        for (int p = 0; p < 7; p++)
        {
            ochered[p] = 0;
        }
        ochered[0] = 1;
        int k = 1;
        for (int i = 0; i< 7; i++)
        {
            for (int j = 0; j < 7;j++)
            {
                if (myArr[i, j] == 1)
                {
                    bool flag = true;
                    for (int x = 0; x < 7; x++)
                    {
                        if (ochered[x] == j)
                            flag = false;
                    }
                    if (flag == true && k <= 6)
                    {
                        ochered[k] = j;
                        k = k + 1;
                    }
                }
            }
        }
        for (int i = 0; i < 7; i++)
        {
            Console.Write(ochered[i] + " ");
        }
		Console.WriteLine();
        ArrayList list = new ArrayList();
        for(int i = 0; i < 6; i++)
        {
            for(int j = 0; j < 7; j++)
            {
                if(myArr[ochered[i] - 1,j] == 1)
                {
					bool flg1 = false;
                    if(flg1 == false)
                    {
                        list.AddRange(new int[]{ochered[i], j + 1});
						flg1 = true;
                    }
                }
            }
		}
        for(int i = 0; i < list.Count; i++)
        {
            Console.Write(list[i] + " ");
        }
	}
