# testrepo
Hello
Hello from fork2
hello from fork3

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null


curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg


echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null


import java.util.Scanner;

public class calc {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        System.out.print("Enter first number: ");
        int num1 = sc.nextInt();
        
        System.out.print("Enter second number: ");
        int num2 = sc.nextInt();
        
        int sum = num1 + num2;
        int product = num1 * num2;
        
        System.out.println("Addition: " + sum);
        System.out.println("Multiplication: " + product);
        
        sc.close();
    }
}




sudo FROM ubuntu
sudo RUN apt update -y
sudo RUN apt install default-jre -y
sudo RUN mkdir /myapp
sudo COPY calc.java /myapp/
sudo CMD ["java", "/myapp/calc"]


FROM ubuntu
RUN apt update -y
RUN apt install default-jdk -y  # Install JDK (Java Development Kit) for compiling Java code
RUN mkdir /myapp
COPY calc.java /myapp/
WORKDIR /myapp
RUN javac calc.java  # Compile the Java file to generate the .class file
CMD ["java", "calc"]  # Run the compiled class file

