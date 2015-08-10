# threading-Examples

public class testthread extends Thread{
	private Thread t;
	private String threadname;
	testthread(String name)
	{
		threadname=name;
		System.out.println("creating"+threadname);
	}
	public void run()
	{
		System.out.println("running"+threadname);
		try{
			for(int i=0;i<5;i++){
				System.out.println(i);
				Thread.sleep(90);
			}
		}
		catch(Exception e){
		System.out.println("unexcepted exception");
		}
		System.out.println("thread exiting"+threadname);
	}
	public void start(){
		System.out.println("starting"+threadname);
		if(t==null)
			t=new Thread(this,threadname);
		t.start();
	}
	
	public static void main(String[] args) {
		testthread t1=new testthread("Thread-1");
		t1.start();
		testthread t2=new testthread("Thread-2");
		t2.start();
	}

}

