# NestedList
use nested list and loops to check an array

using System;
using System.Linq;
using System.IO;
using System.Text;
using System.Collections;
using System.Collections.Generic;

/**
 * Don't let the machines win. You are humanity's last hope...
 **/
class Player
{
    static void Main(string[] args)
    {
        int width = int.Parse(Console.ReadLine()); // the number of cells on the X axis
        int height = int.Parse(Console.ReadLine()); // the number of cells on the Y axis
        Console.Error.Write(width + " " + height);
        List<List<char>> listCells = new List<List<char>>();
        
        for (int k = 0; k < height; k++)
        {
            string line = Console.ReadLine(); // width characters, each either 0 or .
            List <char> subList = new List<char>(line.ToCharArray());
            listCells.Add(subList);
        }
        
int i = 0, j = 0;

        for (int x = 0; x < height; x++)
        {
            for (int y = 0; y <width; y++)
            {
                if (listCells[x][y] == '0')
                {
                    Console.Write(i + " " + j + " ");
                    
                    //rightside
                    int k = 1;
                    while (y + k < width)
                    {
                        if (listCells[x][y+k] == '.')
                        {
                            k++;
                        }
                        else if (listCells[x][y+k] == '0')
                        {
                            Console.Write(i+k + " " + j + " ");
                            break;
                        }
                    }
                    if (y + k >= width)
                    { 
                      Console.Write("-1 -1 ");
                    }
                    
                    //bottom side
                    k = 1;
                    while (x + k < height)
                    {
                        if (listCells[x+k][y] == '.')
                        {
                            k++;
                        }
                        else if (listCells[x+k][y] == '0')
                        {
                            Console.Write(i + " " + (j+k) + " ");
                            break;
                        }
                    }
                    if (x + k >= height)
                    { 
                      Console.Write("-1 -1 ");
                    }
                    Console.WriteLine();
                  
                }
                  i++;
            }
            i = 0;
            j++;
        }

        // Write an action using Console.WriteLine()
        // To debug: Console.Error.WriteLine("Debug messages...");


        // Three coordinates: a node, its right neighbor, its bottom neighbor
       
    }
}
