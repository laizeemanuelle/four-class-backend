# four-class-backend
Code Four Class

using System; using System.IO;


namespace Alunos
{
    class Program
    {
        static void Main(string[] args)

        {
            string fileName = @"C:\Users\ciee.lab\Desktop\turma01.txt";


            //Create a StreamReader
            using (StreamReader reader = new StreamReader(fileName))
            {

                string line;
                //Read line by line
                while ((line = reader.ReadLine()) != null)
                {
                    var aluno = line.Split('|');
                    var matricula = aluno[0];
                    var nome = aluno[1];
                    decimal nota = Decimal.Parse(aluno[2], System.Globalization.CultureInfo.InvariantCulture);


                    Console.Write(matricula + " " + nome + " Nota: " + nota + "Status");

                    if (nota < 7)
                    {
                        Console.Write("Reprovado");
                    }

                    else
                    {
                        Console.Write("Aprovado");
                    }


                }


            }
        }
    }
}



