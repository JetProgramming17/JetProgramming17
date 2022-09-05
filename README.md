import java.util.ArrayList;
import java.util.Scanner;

class Product{
private String code;
private String name;
private String categeory;
private int warranty;
private int price;
private int stockLevels;
private String supplier;

public Product() {
}

public Product(String code, String name, String categeory, int warranty, int price, int stockLevels, String supplier) {
this.code = code;
this.name = name;
this.categeory = categeory;
this.warranty = warranty;
this.price = price;
this.stockLevels = stockLevels;
this.supplier = supplier;
}

public void setCode(String code) {
this.code = code;
}

public void setName(String name) {
this.name = name;
}

public void setCategeory(String categeory) {
this.categeory = categeory;
}

public void setWarranty(int warranty) {
this.warranty = warranty;
}

public void setPrice(int price) {
this.price = price;
}

public void setStockLevels(int stockLevels) {
this.stockLevels = stockLevels;
}

public void setSupplier(String supplier) {
this.supplier = supplier;
}

public String getCode() {
return code;
}

public String getName() {
return name;
}

public String getCategeory() {
return categeory;
}

public int getWarranty() {
return warranty;
}

public int getPrice() {
return price;
}

public int getStockLevels() {
return stockLevels;
}

public String getSupplier() {
return supplier;
}

@Override
public String toString() {
  
return "Product{" + "code=" + code + ", name=" + name + ", categeory=" + categeory + ", warranty=" + warranty + ", price=" + price + ", stockLevels=" + stockLevels + ", supplier=" + supplier + '}';
}
  
  
}

public class NewClass2 {
static ArrayList<Product> list;
public static void main(String str[]){
int choice;
// Declaring the ArrayList
list = new ArrayList<Product>();
do{
displayMenu();
Scanner sc = new Scanner(System.in);
System.out.print("Enter choice : ");
choice = sc.nextInt();
  
switch(choice){
case 1:
Product newProduct = createProduct();
list.add(newProduct);
break;
case 2:
serachProduct();
break;
case 3:
updateProduct();
break;
case 4:
deleteProduct();
break;
}
System.out.print("Enter (1) to lanch menu or any other key to exit : ");
choice = sc.nextInt();
  

}while(choice==1);
  
}
public static void displayMenu(){
System.out.println(" 1-> Insert Item ");
System.out.println(" 2-> Serach Item ");
System.out.println(" 3-> Update Item ");
System.out.println(" 4-> Delate Item ");
}

private static Product createProduct() {
Product newProduct = new Product();
Scanner sc = new Scanner(System.in);
System.out.print("Enter the Product code : ");
newProduct.setCode(sc.next());
System.out.print("Enter the Product Name : ");
newProduct.setName(sc.next());
System.out.print("Enter the Product category : ");
newProduct.setCategeory(sc.next());
System.out.print("Enter the Product warranty : ");
newProduct.setWarranty(sc.nextInt());
System.out.print("Enter the Product price : ");
newProduct.setPrice(sc.nextInt());
System.out.print("Enter the Product Stock Levels : ");
newProduct.setStockLevels(sc.nextInt());
System.out.print("Enter the Product suppiler : ");
newProduct.setSupplier(sc.next());
  
return newProduct;
}

private static void serachProduct() {
Scanner sc = new Scanner(System.in);
String code;
int productFound =0;
System.out.print("Please enter the code to search : ");
code = sc.next();
for(int i = 0;i<list.size();i++){
if(list.get(i).getCode().equalsIgnoreCase(code)){
productFound++;
System.out.println("***************************************************************************************");
System.out.println("PRODUCT SERACH RESULTS");
System.out.println("***************************************************************************************");
System.out.println("PRODUCT CODE : "+list.get(i).getCode()) ;
System.out.println("PRODUCT NAME : "+list.get(i).getName());
System.out.println("PRODUCT CATEGEORY : "+list.get(i).getCategeory());
System.out.println("PRODUCT WARRANTY : "+list.get(i).getWarranty()+" years");
System.out.println("PRODUCT PRICE : R "+list.get(i).getPrice());
System.out.println("PRODUCT STOCK LEVELS : "+list.get(i).getStockLevels());
System.out.println("PRODUCT SUPPILER : "+list.get(i).getSupplier());
System.out.println("***************************************************************************************");
}
}
if( productFound == 0){
System.out.println("The product cannot be located. Invalid product");
}

}

private static void deleteProduct() {
Scanner sc = new Scanner(System.in);
String code;
String confirm;
System.out.print("Please enter the code for delete the product : ");
code = sc.next();
int productFound =0;
for(int i = 0;i<list.size();i++){
if(list.get(i).getCode().equalsIgnoreCase(code)){
productFound++;
System.out.print("Confirm that you want to delete the product(Yes/No) : ");
confirm = sc.next();
if(confirm.equalsIgnoreCase("YES")){
list.remove(i);
System.out.println("The product code "+ code+ " has been successfully deleted.");
}else{
System.out.println("The product code "+ code+ " can not deleted.");
}
}
}
if( productFound == 0){
System.out.println("The product cannot be located. Invalid product");
}

}

private static void updateProduct() {
Scanner sc = new Scanner(System.in);
String code;
int productFound =0;
String confirm;
System.out.print("Please enter the code to update the product : ");
code = sc.next();
for(int i = 0;i<list.size();i++){
if(list.get(i).getCode().equalsIgnoreCase(code)){
productFound++;
System.out.print("Updtae the product warranty(Yes/No): ");
confirm = sc.next();
if(confirm.equalsIgnoreCase("YES")){
System.out.print("Updated warranty : ");
list.get(i).setWarranty(sc.nextInt());
System.out.println("The warranty of product code "+ code+ " has been successfully updated.");
}

System.out.print("Updtae the product price(Yes/No) : ");
confirm = sc.next();
if(confirm.equalsIgnoreCase("YES")){
System.out.print("Updated price : ");
list.get(i).setPrice(sc.nextInt());
System.out.println("The price of product code "+ code+ " has been successfully updated.");
}
System.out.print("Updtae the product stock level(Yes/No) : ");
confirm = sc.next();
if(confirm.equalsIgnoreCase("YES")){
System.out.print("Updated stock level : ");
list.get(i).setStockLevels(sc.nextInt());
System.out.println("The stock level of product code "+ code+ " has been successfully updated.");
}
}
}
if( productFound == 0){
System.out.println("The product cannot be located. Invalid product");
}

}
}
