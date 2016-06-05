
/**
 * 定义一个操作方法类
 * @date 2016.6.1~2016.6.5
 * @author ZTW
 * @version 1.0
 */
import java.io.File;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.ObjectInputStream;
import java.io.ObjectOutputStream;
import java.util.Scanner;

public class TheOperation
{
	
	public void operation(Professional b) 
	{
		explain();
		while(true)
		{
			Scanner input=new Scanner(System.in);
			System.out.println("请输入游戏指令：");
			String playString=input.next();
			if(playString.equals("go"))
			{
				runGame(b);
			}
			else if(playString.equals("useHP"))
			{
				b.useHPDrug();
			}
			else if(playString.equals("useMP"))
			{
				b.useMPDrug();
			}
			else if(playString.equals("query"))
			{
				b.query();
			}
			else if (playString.equals("help")) 
			{
				explain();
			}
			else if(playString.equals("save"))
			{
				save(b);
			}
			else if(playString.equals("exit"))
			{
				save(b);
				System.out.println("退出游戏！");
				break;
			}
			else
			{
				System.out.println("输入的指令不正确，请输入‘help’查询指令说明。");
			}
		}
	}
	public void explain()//定义指令说明方法
	{
		System.out.println("游戏说明：");
		System.out.println("非战斗阶段说明：");
		System.out.println("输入‘go’表示前进，会随机发生事件。");
		System.out.println("输入‘useHP’表示使用HP恢复药剂，恢复30点血量。");
		System.out.println("输入‘useMP’表示使用MP恢复药剂，恢复30点法力。");
		System.out.println("输入‘query’表示查看角色当前属性。");
		System.out.println("输入‘help’表示使用帮助，查看指令说明。");
		System.out.println("输入‘save’表示存档。");
		System.out.println("输入‘exit’表示保存当前角色属性并退出游戏。");
		System.out.println("战斗阶段说明：");
		System.out.println("输入‘attack’表示用普通攻击攻击怪物。");
		System.out.println("输入‘useHP’表示使用HP恢复药剂，恢复30点血量。");
		System.out.println("输入‘useMP’表示使用MP恢复药剂，恢复30点法力。");
		System.out.println("输入‘query’表示查看角色当前属性。");
		System.out.println("输入‘help’表示使用帮助，查看指令说明。");
		System.out.println("输入‘escape’表示撤退，有一定几率成功脱离战斗。");
	}
	
	public void runGame(Professional b) //定义产生不同情形的方法
	{
		int a=0;
		a=(int)(1+Math.random()*(10-1+1));
		switch(a)
		{
			case 1:
				System.out.println("一路上很平静，什么都没发生！");
				break;
			case 2:
				System.out.println("天气很晴朗，并没有什么事发生！");
				break;
			case 3:
				System.out.println("你在路上看见了一只小浣熊，并与其玩耍了一会。");
				break;
			case 4:
				System.out.println("很幸运，在路边捡到了一个HP药剂！");
				b.setHPdrug();
				break;
			case 5:
				System.out.println("很走运，在草丛里发现了一个MP药剂！");
				b.setMPdrug();
				break;
			case 6:
				System.out.println("与怪物遭遇了，进入战斗！");		//分等级遭遇不同的普通怪物
				if (b.getLevel()<11) 						//1~10
				{
					System.out.println("遭遇史莱姆！");
					fight(b,25,20,5,3,50);
				}
				else if (b.getLevel()<21 && b.getLevel()>10)//11~20
				{
					System.out.println("遭遇蝙蝠！");
					fight(b, 60, 50, 60, 43, 150);
				}
				else if (b.getLevel()<31 && b.getLevel()>20)//21~30
				{
					System.out.println("遭遇硕鼠！");
					fight(b, 130, 80, 120, 80, 300);
				}
				else if (b.getLevel()<41 && b.getLevel()>30)//31~40
				{
					System.out.println("遭遇巨蟒！");
					fight(b, 280, 100, 160, 100, 500);
				}
				else if (b.getLevel()<51 && b.getLevel()>40)//41~50
				{
					System.out.println("遭遇骷髅！");
					fight(b, 580, 120, 220, 140, 650);
				}
				else if (b.getLevel()<61 && b.getLevel()>50)//51~60
				{
					System.out.println("遭遇奇美拉！");
					fight(b, 650, 120, 260, 170, 800);
				}
				else if (b.getLevel()<71 && b.getLevel()>60)//61~70
				{
					System.out.println("遭遇石像鬼！");
					fight(b, 700, 120, 310, 190, 900);
				}
				else if (b.getLevel()<81 && b.getLevel()>70)//71~80
				{
					System.out.println("遭遇骷髅侍卫！");
					fight(b, 800, 120, 360, 220, 1000);
				}
				else if (b.getLevel()<91 && b.getLevel()>80)//81~90
				{
					System.out.println("遭遇骷髅弓箭手！");
					fight(b, 850, 120, 410, 250, 1100);
				}
				else if (b.getLevel()<101 && b.getLevel()>90)//91~100
				{
					System.out.println("遭遇恶魔！");
					fight(b, 900, 150, 460, 280, 1200);
				}
				else
				{
					System.out.println("等级超过100级，程序异常！");
					System.exit(0);
				}
				break;
			case 7:
				System.out.println("与怪物遭遇了，进入战斗！");
				if (b.getLevel()<11) 						//1~10
				{
					System.out.println("遭遇史莱姆！");
					fight(b,25,20,5,3,50);
				}
				else if (b.getLevel()<21 && b.getLevel()>10)//11~20
				{
					System.out.println("遭遇蝙蝠！");
					fight(b, 60, 50, 60, 43, 150);
				}
				else if (b.getLevel()<31 && b.getLevel()>20)//21~30
				{
					System.out.println("遭遇硕鼠！");
					fight(b, 130, 80, 120, 80, 300);
				}
				else if (b.getLevel()<41 && b.getLevel()>30)//31~40
				{
					System.out.println("遭遇巨蟒！");
					fight(b, 280, 100, 160, 100, 500);
				}
				else if (b.getLevel()<51 && b.getLevel()>40)//41~50
				{
					System.out.println("遭遇骷髅！");
					fight(b, 580, 120, 220, 140, 650);
				}
				else if (b.getLevel()<61 && b.getLevel()>50)//51~60
				{
					System.out.println("遭遇奇美拉！");
					fight(b, 650, 120, 260, 170, 800);
				}
				else if (b.getLevel()<71 && b.getLevel()>60)//61~70
				{
					System.out.println("遭遇石像鬼！");
					fight(b, 700, 120, 310, 190, 900);
				}
				else if (b.getLevel()<81 && b.getLevel()>70)//71~80
				{
					System.out.println("遭遇骷髅侍卫！");
					fight(b, 800, 120, 360, 220, 1000);
				}
				else if (b.getLevel()<91 && b.getLevel()>80)//81~90
				{
					System.out.println("遭遇骷髅弓箭手！");
					fight(b, 850, 120, 410, 250, 1100);
				}
				else if (b.getLevel()<101 && b.getLevel()>90)//91~100
				{
					System.out.println("遭遇恶魔！");
					fight(b, 900, 150, 460, 280, 1200);
				}
				else
				{
					System.out.println("等级超过100级，程序异常！");
					System.exit(0);
				}
				break;
			case 8:
				System.out.println("与怪物遭遇了，进入战斗！");
				if (b.getLevel()<11) 						//1~10
				{
					System.out.println("遭遇史莱姆！");
					fight(b,25,20,5,3,50);
				}
				else if (b.getLevel()<21 && b.getLevel()>10)//11~20
				{
					System.out.println("遭遇蝙蝠！");
					fight(b, 60, 50, 60, 43, 150);
				}
				else if (b.getLevel()<31 && b.getLevel()>20)//21~30
				{
					System.out.println("遭遇硕鼠！");
					fight(b, 130, 80, 120, 80, 300);
				}
				else if (b.getLevel()<41 && b.getLevel()>30)//31~40
				{
					System.out.println("遭遇巨蟒！");
					fight(b, 280, 100, 160, 100, 500);
				}
				else if (b.getLevel()<51 && b.getLevel()>40)//41~50
				{
					System.out.println("遭遇骷髅！");
					fight(b, 580, 120, 220, 140, 650);
				}
				else if (b.getLevel()<61 && b.getLevel()>50)//51~60
				{
					System.out.println("遭遇奇美拉！");
					fight(b, 650, 120, 260, 170, 800);
				}
				else if (b.getLevel()<71 && b.getLevel()>60)//61~70
				{
					System.out.println("遭遇石像鬼！");
					fight(b, 700, 120, 310, 190, 900);
				}
				else if (b.getLevel()<81 && b.getLevel()>70)//71~80
				{
					System.out.println("遭遇骷髅侍卫！");
					fight(b, 800, 120, 360, 220, 1000);
				}
				else if (b.getLevel()<91 && b.getLevel()>80)//81~90
				{
					System.out.println("遭遇骷髅弓箭手！");
					fight(b, 850, 120, 410, 250, 1100);
				}
				else if (b.getLevel()<101 && b.getLevel()>90)//91~100
				{
					System.out.println("遭遇恶魔！");
					fight(b, 900, 150, 460, 280, 1200);
				}
				else
				{
					System.out.println("等级超过100级，程序异常！");
					System.exit(0);
				}
				break;
			case 9:
				System.out.println("与怪物遭遇了，进入战斗！");
				if (b.getLevel()<11) 						//1~10
				{
					System.out.println("遭遇史莱姆！");
					fight(b,25,20,5,3,50);
				}
				else if (b.getLevel()<21 && b.getLevel()>10)//11~20
				{
					System.out.println("遭遇蝙蝠！");
					fight(b, 60, 50, 60, 43, 150);
				}
				else if (b.getLevel()<31 && b.getLevel()>20)//21~30
				{
					System.out.println("遭遇硕鼠！");
					fight(b, 130, 80, 120, 80, 300);
				}
				else if (b.getLevel()<41 && b.getLevel()>30)//31~40
				{
					System.out.println("遭遇巨蟒！");
					fight(b, 280, 100, 160, 100, 500);
				}
				else if (b.getLevel()<51 && b.getLevel()>40)//41~50
				{
					System.out.println("遭遇骷髅！");
					fight(b, 580, 120, 220, 140, 650);
				}
				else if (b.getLevel()<61 && b.getLevel()>50)//51~60
				{
					System.out.println("遭遇奇美拉！");
					fight(b, 650, 120, 260, 170, 800);
				}
				else if (b.getLevel()<71 && b.getLevel()>60)//61~70
				{
					System.out.println("遭遇石像鬼！");
					fight(b, 700, 120, 310, 190, 900);
				}
				else if (b.getLevel()<81 && b.getLevel()>70)//71~80
				{
					System.out.println("遭遇骷髅侍卫！");
					fight(b, 800, 120, 360, 220, 1000);
				}
				else if (b.getLevel()<91 && b.getLevel()>80)//81~90
				{
					System.out.println("遭遇骷髅弓箭手！");
					fight(b, 850, 120, 410, 250, 1100);
				}
				else if (b.getLevel()<101 && b.getLevel()>90)//91~100
				{
					System.out.println("遭遇恶魔！");
					fight(b, 900, 150, 460, 280, 1200);
				}
				else
				{
					System.out.println("等级超过100级，程序异常！");
					System.exit(0);
				}
				break;
			case 10:
				System.out.println("遭遇怪物小头目！");
				if (b.getLevel()<11) 
				{
					System.out.println("遭遇巨型史莱姆！");
					fight(b,100,100,30,20,200);
				}
				else if (b.getLevel()<21 && b.getLevel()>10) 
				{
					System.out.println("遭遇大蝙蝠！");
					fight(b, 200, 100, 80, 50, 400);
				}
				else if (b.getLevel()<31 && b.getLevel()>20)
				{
					System.out.println("遭遇硕鼠头目！");
					fight(b, 300, 100, 130, 80, 600);
				}
				else if (b.getLevel()<41 && b.getLevel()>30)
				{
					System.out.println("遭遇巨蟒头目！");
					fight(b, 400, 100, 180, 110, 800);
				}
				else if (b.getLevel()<51 && b.getLevel()>40)
				{
					System.out.println("遭遇骷髅队长！");
					fight(b, 500, 100, 230, 140, 1000);
				}
				else if (b.getLevel()<61 && b.getLevel()>50)
				{
					System.out.println("遭遇奇美拉头目！");
					fight(b, 600, 100, 280, 170, 1200);
				}
				else if (b.getLevel()<71 && b.getLevel()>60)
				{
					System.out.println("遭遇大型石像鬼！");
					fight(b, 700, 100, 330, 200, 1400);
				}
				else if (b.getLevel()<81 && b.getLevel()>70)
				{
					System.out.println("遭遇骷髅侍卫长！");
					fight(b, 800, 100, 380, 230, 1600);
				}
				else if (b.getLevel()<91 && b.getLevel()>80) 
				{
					System.out.println("遭遇骷髅弓箭手领队！");
					fight(b, 900, 100, 430, 260, 1800);
				}
				else if (b.getLevel()<100 && b.getLevel()>90) 
				{
					System.out.println("遭遇魔王！");
					fight(b, 1000, 100, 480, 290, 2000);
				}
				else if (b.getLevel()==100) 
				{
					System.out.println("等级达到100级！感谢你的支持！");
					System.out.println("作为达到100级的勇士，程序猿要对你进行考验，觉悟吧！");
					fight(b, 1995, 500, 512, 425, 0);
					System.out.println("很好，你通过了我的考验，如果你有任何的意见和建议，请联系我：QQ496379589");
				}
				else
				{
					System.out.println("等级超过100级！程序异常！");
					System.exit(0);
				}
				break;
			default:
				System.out.println("游戏程序产生随机数时发生异常！");
				System.exit(0);
				break;
		}
	}
	public void fight(Professional b,int mHP,int mMP,int mAtt,int mDef,int mExp)//定义战斗的方法接收相关的战斗参数(角色对象，怪物属性:HP生命值,MP法力值,Att攻击力,Def防御力,Exp经验值)
	{
		int hurt=b.attack-mDef;//定义角色造成的伤害，如果对怪无伤害，则强制扣一血
		if (hurt<0) 
		{
			hurt=1;
		}
		int mhurt=mAtt-b.defense;//定义怪物造成的伤害，如果对角色无伤害，则强制扣一血
		if (mhurt<0)
		{
			mhurt=1;
		}
		while (true) 
		{
			System.out.println("请输入战斗指令：（输入‘help’查看指令说明）");
			Scanner input=new Scanner(System.in);
			String fightString=input.next();
			if(fightString.equals("help"))//查看帮助
			{
				explain();
			}
			else if(fightString.equals("query"))//查询当前角色状态
			{
				b.query();
			}
			else if(fightString.equals("attack"))//攻击
			{
				System.out.println(b.getName()+"攻击了怪物！");
				mHP=mHP-hurt;							//角色攻击怪物
				System.out.println("怪物当前血量："+mHP);
				if (mHP<=0)								//怪物死亡,战斗胜利获得经验
				{
					System.out.println("战斗胜利！");
					b.addExp(mExp);
					int fightEnd=0;
					fightEnd=(int)(1+Math.random()*(3-1+1));
					if (fightEnd==1)
					{
						System.out.println("获得药剂补给！");
						b.setHPdrug();
						b.setMPdrug();
					}
					save(b);
					break;
				}
				else									//怪物未死亡，怪物攻击回合
				{
					System.out.println("怪物攻击了"+b.getName());
					b.HP=b.HP-mhurt;
					if (b.HP<=0)//判断角色死亡
					{
						System.out.println("Game Over!");
						System.exit(0);
						break;
					}
					else
					{
						System.out.println("角色当前生命值："+b.getHP()+"角色当前法力值："+b.getMP());
					}
				}
			}
			else if (fightString.equals("useHP"))//使用HP药剂
			{
				b.useHPDrug();							//角色回合使用药物
				b.HP=b.HP-mhurt;						//怪物回合攻击角色
				if (b.HP<=0)//判断角色死亡
				{
					System.out.println("Game Over!");
					System.exit(0);
					break;
				}
				else
				{
					System.out.println("角色当前生命值："+b.getHP()+"角色当前法力值："+b.getMP());
				}
			}
			else if(fightString.equals("useMP"))//使用MP药剂
			{
				b.useMPDrug();					//角色使用MP药剂回合
				b.HP=b.HP-mhurt;				//怪物回合攻击角色
				if (b.HP<=0)
				{
					System.out.println("Game Over!");
					System.exit(0);
					break;
				}
				else
				{
					System.out.println("角色当前生命值："+b.getHP()+"角色当前法力值："+b.getMP());
				}
			}
			else if(fightString.equals("escape"))//撤离战斗
			{
				int esc=0;
				esc=(int)(1+Math.random()*(3-1+1));
				if(esc==2)
				{
					System.out.println("逃离失败！");		//角色逃离失败回合
					b.HP=b.HP-mhurt;					//怪物回合攻击角色
					if (b.HP<=0)//判断角色死亡
					{
						System.out.println("Game Over!");
						System.exit(0);
						break;
					}
					else
					{
						System.out.println("角色当前生命值："+b.getHP()+"角色当前法力值："+b.getMP());
					}
				}
				else
				{
					System.out.println("撤离成功，已脱离战斗！");
					break;
				}
			}
			else//指令错误
			{
				System.out.println("输入的战斗指令有误，请输入‘help’确认后重试！");
			}
		}
	}
	public void save(Professional b) 
	{
		try 
		{
			ObjectOutputStream oos=new ObjectOutputStream(new FileOutputStream("./player.dat"));
			oos.writeObject(b);
			oos.close();
			System.out.println("保存成功！");
		} 
		catch (Exception e) 
		{
			System.out.println("抱歉！存档失败，游戏进度丢失！");// TODO: handle exception
		}
	}
}
