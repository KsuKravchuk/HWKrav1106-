# HWKrav1106-
package JHomeWork0206;

import java.util.*;

public class HWKrav1106 {
    private String name;
    private String departnent;
    private int age;
    private  int salary;

    public HWKrav1106(String name, String departnent, int age, int salary) {
        this.name = name;
        this.departnent = departnent;
        this.age = age;
        this.salary = salary;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        HWKrav1106 that = (HWKrav1106) o;
        return age == that.age && salary == that.salary && Objects.equals(name, that.name) && Objects.equals(departnent, that.departnent);
    }

    @Override
    public int hashCode() {
        return Objects.hash(name, departnent, age, salary);
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getDepartnent() {
        return departnent;
    }

    public void setDepartnent(String departnent) {
        this.departnent = departnent;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public int getSalary() {
        return salary;
    }

    public void setSalary(int salary) {
        this.salary = salary;
    }

    public static void main(String[] args) {
       HWKrav1106 hwKrav1106 = new HWKrav1106("Ebony Guerrero", "Salary", 19, 2550);
        HWKrav1106 hwKrav11061 = new HWKrav1106("Adnan Day", "Salary", 21, 3800);
        HWKrav1106 hwKrav11062 = new HWKrav1106("Rex Levy", "Salary", 41, 5000);
        HWKrav1106 hwKrav11063 = new HWKrav1106("Poppy Cunningham", "Salary", 20, 4450);
        HWKrav1106 hwKrav11064 = new HWKrav1106("Abbey Stephens", "Salary", 35, 1480);
        HWKrav1106 hwKrav11065 = new HWKrav1106("Carter Sutherland", "Salary", 40, 2450);
        HWKrav1106 hwKrav11066 = new HWKrav1106("Aayan Bennett", "Salary", 39, 450);
        HWKrav1106 hwKrav11067 = new HWKrav1106("Mia Tompson", "Salary", 25, 2500);
        HWKrav1106 hwKrav11068 = new HWKrav1106("Kristian Braun","Salaru", 42, 4100);

        Generator generator = new Generator();
        List<HWKrav1106> hwKrav1106s = generator.generatorEmployees(hwKrav11061,hwKrav11062,hwKrav11065, hwKrav11063, hwKrav1106,hwKrav11064,hwKrav11066,
                hwKrav11067, hwKrav11068);
        System.out.println(hwKrav1106s);

        DataBase dataBase = new DataBase();
        dataBase.addHWKrav1106(hwKrav1106s);
        dataBase.printDataBase();

    }

    @Override
    public String toString() {
        return "HWKrav1106{" +
                "name='" + name + '\'' +
                ", departnent='" + departnent + '\'' +
                ", age=" + age +
                ", salary=" + salary +
                '}';
    }
}
 class Generator {
    public static List<HWKrav1106> generatorEmployees(HWKrav1106... hwKrav1106s){
        List<HWKrav1106> list = new ArrayList<>(Arrays.asList(hwKrav1106s));
        return list;
    }
 }
 class DataBase{
    private Map<Integer, HWKrav1106> dataBase;
    public DataBase(){
        dataBase = new TreeMap<>();
    }
    public void addHWKrav1106 (List<HWKrav1106> list){
        int key = 1;

        for (HWKrav1106 hwKrav1106:list){
            dataBase.put(key++,hwKrav1106);
        }

    }
    public void printDataBase(){
        for (Map.Entry<Integer, HWKrav1106> entry:dataBase.entrySet()){

            System.out.println(entry);

        }
    }
 }
