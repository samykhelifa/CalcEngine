
```java
public class MathEquation {
    private double leftVal;
    private double rightVal;
    private char opCode;
    private double result;

    public double getLeftVal() {return leftVal;}
    public void setLeftVal(double leftVal) {this.leftVal = leftVal;}
    public double getRightVal() {return rightVal;}
    public void setRightVal(double rightVal) {this.rightVal = rightVal;}
    public char getOpCode() {return opCode;}
    public void setOpCode(char opCode) {this.opCode = opCode;}

    public double getResult() { return result;}
    
    /******************** constructors added ******************/
    
    public MathEquation() {}

    public MathEquation(char opCode) {
        this.opCode = opCode;
    }

    public MathEquation(char opCode, double leftVal, double rightVal) {
        this(opCode);
        this.leftVal = leftVal;
        this.rightVal = rightVal;
    }
    
    /****************************************************************/

    public void execute() {
        switch(opCode) {
            case 'a':
                result = leftVal + rightVal;
                break;
            case 's':
                result = leftVal - rightVal;
                break;
            case 'd':
                result = rightVal != 0.0d ? leftVal / rightVal : 0.0d;
                break;
            case 'm':
                result = leftVal * rightVal;
                break;
            default:
                System.out.println("Error - invalid opCode");
                result = 0.0d;
                break;
        }

    }
}
```

```java

public class Main {

    public static void main(String[] args) {
        MathEquation[] equations = new MathEquation[4];
  /********************************* without constructors
        equations[0] = create(100.0d, 50.0d, 'd');
        equations[1] = create(25.0d, 92.0d, 'a');
        equations[2] = create(225.0d, 17.0d, 's');
        equations[3] = create(11.0d, 3.0d, 'm');
  **************************************************/
        equations[0] = new MathEquation('d', 100.0d, 50.0d);
        equations[1] = new MathEquation('a', 25.0d, 92.0d);
        equations[2] = new MathEquation('s', 225.0d, 17.0d);
        equations[3] = new MathEquation('m', 11.0d, 3.0d);
  
  

        for(MathEquation equation : equations) {
            equation.execute();
            System.out.print("result = ");
            System.out.println(equation.getResult());
        }
    }
/********************************* without constructors
    public static MathEquation create(double leftVal, double rightVal, char opCode) {
        MathEquation equation = new MathEquation();
        equation.setLeftVal(leftVal);
        equation.setRightVal(rightVal);
        equation.setOpCode(opCode);

        return equation;
    }
    ************************************************************/
}
```



