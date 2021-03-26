# Binomial-Distribution-
Calculations for Binomial Distribution, Expected Values, Variance, and Combination formula

package apple;

public class orange {
	public static void main(String args[]) {
		double answer = binomialDistribution(  14,15,0.8 ) - binomialDistribution(  13,15,0.8 ) ;       ///@param (x,n,p)  [REMEMBER TO MINUS IF EXECT!!!]
		
		System.out.println(answer);
		System.out.println(xFact(6)/((xFact(2))*(xFact(4))));	
		expectedValue( 100,0.2 ) ;                                ///@param (n,p)

	}
	public static double xFact(double x) {                      //////Combination formula
		if(x==0 || x==1)return 1;
		return x*xFact(x-1);
	}
	public static double binomialDistribution(double x, double n, double p) {     //////binomial distribution (calc CUMILATIVE)
		if(x < 0)return 0.0;
		double comb = xFact(n)/((xFact(x))*(xFact(n-x)));
		return ((comb) * (Math.pow(p,x)) * (Math.pow(1-p,n-x))) + binomialDistribution(x-1, n, p);	
	}
	public static void expectedValue(double n, double p) {      /////Expected Value , Variance , Standard Deviation
		double expVal = n*p;
		double Variance = n*p*(1-p);
		double stndDev = Math.sqrt(Variance);
		System.out.println("E(X) = " + expVal + "\nV(X) = " + Variance + "\nStandard Deviation = " + stndDev);
	}
}
