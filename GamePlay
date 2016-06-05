
/**
 *	@date 2016.6.5
 *	@author ZTW
 *	
 */
import java.io.File;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.ObjectInputStream;
import java.io.ObjectOutputStream;
import java.util.Scanner;

public class GamePlay
{
	static int gameStart=0;
	static GamePlay gp=new GamePlay();
	public static void main(String[] args)
	{
		for(gameStart=0;gameStart!=1;)
		{
			gp.startGame();
		}
	}
	
	public void startGame() //定义选择登录或注册游戏的方法
	{
		Scanner input=new Scanner(System.in);
		System.out.println("输入‘login’进入登录界面，输入‘register’进入注册界面：");
		String op=input.next();
		if(op.equals("login"))
		{
			gp.gameStart=1;
			login();
		}
		else if(op.equals("register"))
		{
			gp.gameStart=1;
			register();
		}
		else
		{
			System.out.println("输入的指令不正确，请确认后再试！");
			gameStart=0;
		}
	}
	public void login() //定义一个登录方法
	{
		System.out.println("游戏登录！");
		System.out.println("请输入账号：");
		Scanner input=new Scanner(System.in);
		String No=input.next();
		System.out.println("请输入密码：");
		String password=input.next();
		try 
		{
			File checkFile=new File("./user.dat");
			if (checkFile.exists()) 
			{
				ObjectInputStream ois=new ObjectInputStream(new FileInputStream("./User.dat"));
				ID user=(ID) ois.readObject();
				ois.close();
				String userNo=user.getNo();
				String userPw=user.getPassword();
				
				if(userNo.equals(No) && userPw.equals(password))//判断账号，密码是否匹配
				{
					try 
					{
						checkFile=new File("./user.dat");
						ObjectInputStream ois2=new ObjectInputStream(new FileInputStream("./player.dat"));
						Professional b=(Professional) ois2.readObject();
						ois.close();
						System.out.println("登录成功！");
						TheOperation to=new TheOperation();
						to.operation(b);
					} 
					catch (Exception e) 
					{
						// TODO: handle exception
					}
				}
				else
				{
					System.out.println("帐号与密码不匹配，登录游戏失败！");
				}

			}
			else 
			{
				System.out.println("未存入任何账号，请先注册！");
			}
		}
		catch (Exception e)
		{
			// TODO: handle exception
		}
	}
	public void register()//定义一个注册方法
	{
		System.out.println("注册游戏！本系统只支持单账号注册，注册第二个账号会自动覆盖之前的账号！");
		ID user=new ID();
		System.out.println("请设置登录账号：");
		Scanner input=new Scanner(System.in);
		String no=input.next();
		user.setNo(no);
		System.out.println("请设置登录密码：");
		String pw=input.next();
		user.setPassword(pw);
		try
		{
			ObjectOutputStream oos=new ObjectOutputStream(new FileOutputStream("./User.dat"));
			oos.writeObject(user);
			oos.close();
			System.out.println("注册成功！");
			Professional b=null;	//定义职业类对象b
			try 
			{
				System.out.println("请选择角色职业：");
				System.out.println("berserker;saber");
				String pp=input.next();
				if (pp.equals("berserker")) {
					b=new Berserker();
				}
				else if (pp.equals("saber")) {
					b=new Saber();
				}
				System.out.println("请输入角色姓名：");
				String name=input.next();
				b.setName(name);
				ObjectOutputStream oos2=new ObjectOutputStream(new FileOutputStream("./player.dat"));
				oos2.writeObject(b);
				oos2.close();
				System.out.println("创建角色成功！");
			} 
			catch (Exception e) 
			{
				System.out.println("创建角色时发生异常！");
			}
			login();
		} 
		catch (Exception e)
		{
			// TODO: handle exception
		}
	}
}
