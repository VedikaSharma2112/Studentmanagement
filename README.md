# Studentmanagement

import java.util.*;
class Student
{
     String name;
	 String cor;
	 int roll;
	 Student(String name, String cor, int roll)
	 {
	     this.name = name;
		 this.cor = cor;
		 this.roll = roll;
	 }
	 
	 void disp()
	 {
	     System.out.println("Name:" +name);
		 System.out.println("Course:" +cor);
		 System.out.println("Roll:" +roll);
	 }
}

class Manage
{
    public static void main(String arr[])
    {
	   Scanner sc = new Scanner(System.in);
	   Student[] student = new Student[100];
	   int count = 0;
	   int opt;
	   while(true)
	   {
	      System.out.println("Enter Your Option:");
		  System.out.println("1. Add Student Detail");
		  System.out.println("2. View Student Detail");
		  System.out.println("3. Delete Student Detail");
		  System.out.println("4. Exit");
		  System.out.println("Option:");
		  opt = sc.nextInt();
		  sc.nextLine();
		  switch(opt)
		  {
		      case 1:
			         System.out.println("  Add Student Detail  ");
					 System.out.println("Enter Name Of Student:");
					 String name = sc.nextLine();
					 System.out.println("Enter Course Name:");
					 String cor = sc.nextLine();
					 System.out.println("Enter Roll Of Student:");
					 int roll = sc.nextInt();
					 student[count] = new Student(name, cor, roll);
					 count++;
					 System.out.println("Detail Added Successfully!");
					 break;
					 
				case 2:
				       System.out.println("  Student List  ");
                       if(count == 0)
                       {
                           System.out.println("No Student To Display");
                       }
                       else
                       {
                            for(int i = 0; i < count; i++)
                            {
                                student[i].disp();
                            }
                       }
                       break;

                case 3:
                       System.out.println("Enter Roll To Delete:");
                       int deleteRoll = sc.nextInt();
                       boolean found = false;
                       for(int i = 0; i < count; i++)
                       {
                           if(student[i].roll == deleteRoll)
                           {
                               for(int j = i; j < count - 1; j++)
                               {
                                   student[j] = student[j + 1];
                               }
                               student[count - 1] = null;
                               count--;
                               found = true;
                               System.out.println("Student Deleted Successfully");
                            }
                       }
					   break;

                case 4:
                       System.out.println("Exiting....");
                       return;
                 
                default:
                        System.out.println("Invalid Option!");
            }
        }
    }
}	
					 
