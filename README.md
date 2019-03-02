# DocumentMerger

using System;
using System.IO;

namespace DocumentMerger
{
    class MainClass
    {
        public static void Main(string[] args)
        { 
            string current = Directory.GetCurrentDirectory();
            Console.WriteLine("testing   {0}",current);
            
            // filenames
            Console.WriteLine("Test Document Merger");

            Console.WriteLine("new Filename:\n");

            string Filename = Console.ReadLine();

            try
            {   
                using (StreamReader sr = new StreamReader("tom.txt"))
                {
                    String line = sr.ReadToEnd();
                    Console.WriteLine(line);
                }
            }

            catch (IOException e)
            {
                Console.WriteLine("The file could not be read:");
                Console.WriteLine(e.Message);
            }

            Console.WriteLine("Second Filename:\n");

            string SecondFilename = Console.ReadLine();
            
            string FINALOUTPUT = Filename + SecondFilename;

            try
            {
                using (StreamReader sr = new StreamReader("cat.txt"))
                {
                    String line = sr.ReadToEnd();
                    Console.WriteLine(line);
                }
            }
            
            string directory1 = System.IO.Path.GetDirectoryName(FileName)
            string directory2 = System.IO.Path.GetDirectoryName(SecondFilename)
            

            catch (IOException e)
            {
                Console.WriteLine("The file could not be read:");
                Console.WriteLine(e.Message);
            }
            
            string[] file1 = File.ReadAllLines("directory1\Filename.txt");
            string[] file2 = File.ReadAllLines("directory2\SecondFilename.txt");

            using (StreamWriter writer = File.CreateText(@"directory1\FINALOUTPUT.txt"))
            {
                int lineNum = 0;
                while(lineNum < file1.Length || lineNum < file2.Length)
                {
                    if(lineNum < file1.Length)
                    writer.WriteLine(file1[lineNum]);
                    
                    if(lineNum < file2.Length)
                    writer.WriteLine(file2[lineNum]);
                    
                    lineNum++;
                }
            }
        }
    }
}
