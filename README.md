# Try With Resource

* Java introduced try-with-resource feature in Java 7 that helps to close resource automatically after being used.
* In other words, we can say that we don't need to close resources (file, connection, network etc) explicitly, try-with-resource close that automatically by using AutoClosable interface.
* In Java 7, try-with-resources has a limitation that requires resource to declare locally within its block.

### Java 7

        public class Main {
            public static void main(String[] args) {
                
                try(FileOutputStream fileStream = new FileOutputStream("output.txt");){
                    String greeting = "hello";
                    byte b[] = greeting.getBytes();
                    fileStream.write(b);
                    System.out.println("file written!");
                } catch(Exception e) {
                    System.out.println(e);
                }
            }
        }

### Java 9
* try-with-resource is improved in Java 9 and now we can use reference of the resource that is not declared locally.

        public class Main {
            public static void main(String[] args) throws FileNotFoundException {
                
                FileOutputStream fileStream = new FileOutputStream("output.txt");
                try(fileStream){
                    String greeting = "hello";
                    byte b[] = greeting.getBytes();
                    fileStream.write(b);
                    System.out.println("file written!");
                } catch(Exception e) {
                    System.out.println(e);
                }
            }
        }

### Ref
* https://www.javatpoint.com/java-9-try-with-resources
