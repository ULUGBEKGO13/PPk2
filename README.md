#   int[,] myArr = new int[8, 8];
        int [][] list = new int [1][];
        int[] ochered = new int[7];
        bool flg2 = true;
        for(int w = 0; w<1; w++)
        {
            list[w] = new int[2];
        }
        for (int i = 1; i<8; i++)
        {
            for (int j = 1; j<8; j++)
            {
                myArr[i, j] = 0;
                myArr[1, 2] = 1;
                myArr[1, 3] = 1;
                myArr[1, 7] = 1;
                myArr[2, 1] = 1;
                myArr[2, 3] = 1;
                myArr[2, 4] = 1;
                myArr[3, 1] = 1;
                myArr[3, 2] = 1;
                myArr[4, 5] = 1;
                myArr[4, 2] = 1;
                myArr[5, 6] = 1;
                myArr[5, 4] = 1;
                myArr[6, 7] = 1;
                myArr[6, 5] = 1;
                myArr[7, 6] = 1;
                myArr[7, 1] = 1;
                Console.Write("{0}\t", myArr[i,j]);
            }
            Console.WriteLine();
        }
        Console.WriteLine();
    
        for (int i = 0; i < 7; i++)
        {
            ochered[i] = 0;
        }
        ochered[0] = 1;
        int k = 1;
        for (int i = 1; i< 8; i++)
        {
            for (int j = 1; j < 8;j++)
            {
                if (myArr[i, j] == 1)
                {
                    bool flag = true;
                    for (int x = 0; x < 7; x++)
                    {
                        if (ochered[x] == j)
                            flag = false;
                    }
                    if (flag == true && k < 7)
                    {
                        ochered[k] = j;
                        k = k + 1;
                    }
                }
            }
        }
        for (int i = 0; i<7;i++)
        {
            Console.Write(ochered[i]);
        }
        int l = 1;
        for(int i =0; i<7; i++)
        {
            for(int j = 0; j<7; j++)
            {
                if(myArr[ochered[k],ochered[k + 1]] == 1)
                {
                    bool flg1 = true;
                    for(int w = 0; w<l; w++)
                    {
                        for(int q = 0; q<2;q++)
                        {
                            if(list[w][q] == list[w + 1][q])
                            {
                                flg1 = false;
                            }
                        }
                    }
                    for(int w = 0; w<l; w++)
                    {
                        if(flg1 == true && flg2 == true)
                        {
                            list[w][0] = ochered[k];
                            list[w][1] = ochered[k + 1];
                            l = l + 1;
                            Array.Resize(ref list, l);
                        }
                    }
                }
                for(int w = 0; w < l; w++)
                {
                    for(int q = 0; q<2; q++)
                    {
                        if(list[w][q] == list[w + 1][q])
                        {
                            flg2 = false;
                        }
                    }
                }
            }
        }
        for(int i = 0; i<l; i++)
        {
            for(int q = 0; q<2; q++)
            {
                Console.Write(list[i][q]);
            }
        }
