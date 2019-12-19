#       int[,] myArr = new int[8, 8];
        int [][] list = new int [1][];
        int[] ochered = new int[7];
        int w = 0;
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
    
        for (int p = 0; p < 7; p++)
        {
            ochered[p] = 0;
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
        for (int p = 0; p<7;p++)
        {
            Console.Write(ochered[p]);
        }
        int q = 2;
        int h = 0;
        for(int i = 1; i < 8; i++)
        {
            for(int j = 1; j < 8; j++)
            {
                if(myArr[ochered[i],j] == 1)
                {
                    bool flg1 = true;
                    if(list.Count >2)
                    {
                        for(int x = 0; x<list.Count; x++)
                        {
                            if(list[x][q] == myArr[i,j])
                            {
                                flg1 = false;
                                h = h + 1;
                            }
                        }
                    }
                    if(flg1 == true && h < 7)
                    {
                        list[w] = new int[]{ochered[k],ochered[k + 1]};
                        Array.Resize(ref list, list.Count() + 1);
                    }
                }
            }
        }
        for(int p = 0; p<l; p++)
        {
            Console.Write(list[p][q]);
        }
