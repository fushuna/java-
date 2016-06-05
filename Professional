
import java.io.Serializable;

/**
 * 所有职业类的抽象父类Professional，具备相关的属性和方法，
 * @date 2016.5.31~2016.6.1
 * @author ZTW
 * @version 1.0
 * 各职业子类需要重写addMaxHP(int lev);addMaxMP(int lev);addAttack(int lev);addDefense(int lev)这四个方法
 */
public abstract class Professional implements Serializable
{
	public int HPdrug=0;//定义HP恢复药剂数量
	public int MPdrug=0;//定义MP恢复药剂数量
	public int level=1;//定义职业等级
	public int exp=0;//定义职业经验
	public int HP=50;//定义当前生命值
	public int maxHP=50;//定义最大生命值
	public int MP=30;//定义当前法力值
	public int maxMP=30;//定义最大法力值
	public int attack=5;//定义职业攻击力
	public int defense=3;//定义职业防御
	public String name="player";//定义角色名
	public void addExp(int exp)//定义获取经验的方法（所有职业经验成长可以相同）
	{
		this.exp=this.exp+exp;
		int needExp=30*(level*level+5*level)-80;//定义经验增长公式，修改30的值可以改变增长曲线
		for(;this.exp>=needExp;)
		{
			this.exp=this.exp-needExp;
			addLevel(1);
		}
	}
	public void addLevel(int lev)//定义升级方法
	{
		if(this.level<=100)
		{
			this.level=this.level+lev;
			addMaxHP(lev);
			addMaxMP(lev);
			addAttack(lev);
			addDefense(lev);
			addHP(maxHP);
			addHP(maxMP);
		}
		else
		{
			this.exp=0;
		}
	}
	abstract void addMaxHP(int lev);//定义最大生命值的成长方法（各职业都不同）
	abstract void addMaxMP(int lev);//定义最大法力值的成长方法（各职业都不同）
	abstract void addAttack(int lev);//定义攻击力的成长方法（各职业都不同）
	abstract void addDefense(int lev);//定义防御力的成长方法（各职业都不同）
	public void addHP(int HPrecharge)//定义HP的回复量	HPrecharge
	{
		HP=HP+HPrecharge;
		if(HP>maxHP)
		{
			HP=maxHP;
			System.out.println("当前HP："+getHP());
		}
		else
		{
			System.out.println("当前HP："+getHP());
		}
	}
	public void addMP(int MPrecharge)//定义MP的回复量	MPrecharge
	{
		MP=MP+MPrecharge;
		if(MP>maxMP)
		{
			MP=maxMP;
			System.out.println("当前MP："+getMP());
		}
		else 
		{
			System.out.println("当前MP："+getMP());
		}
	}
	public void setName(String name)//定义设置角色名的方法
	{
		this.name=name;
	}
	public void setHPdrug()//定义获得HP药剂的方法
	{
		HPdrug+=1;
		System.out.println("HP药剂数量加一！");
	}
	public void setMPdrug()//定义获得MP药剂的方法
	{
		MPdrug+=1;
		System.out.println("MP药剂数量加一！");
	}
	public String getName(){
		return name;
	}
	public int getLevel() {
		return level;
	}
	public int getExp() {
		return exp;
	}
	public int getHP() {
		return HP;
	}
	public int getMaxHP() {
		return maxHP;
	}
	public int getMP() {
		return MP;
	}
	public int getMaxMP() {
		return maxMP;
	}
	public int getAttack() {
		return attack;
	}
	public int getDefense() {
		return defense;
	}
	public int getHPdrug(){
		return HPdrug;
	}
	public int getMPdrug() {
		return MPdrug;
	}
	public void useHPDrug()//定义使用HP药剂的方法
	{
		if (getHPdrug()>0) //当药品数量大于一时使用成功
		{
			HPdrug-=1;
			addHP(10*getLevel());
		}
		else
		{
			System.out.println("HP药剂数量不足，使用失败！");
		}
	}
	public void useMPDrug()
	{
		if(getMPdrug()>0)
		{
			MPdrug-=1;
			addMP(10*getLevel());
		}
		else
		{
			System.out.println("MP药剂数量不足，使用失败！");
		}
	}
	public void query()
	{
		System.out.println("当前角色信息：");
		System.out.println("当前角色名："+getName()+"  当前角色经验："+getExp()+"  当前角色等级："+getLevel()+"  当前角色最大生命值："+getMaxHP()+"  当前角色最大法力值："+getMaxMP()+"  当前角色攻击力："+getAttack()+"  当前角色防御力："+getDefense()+"  当前角色生命值："+getHP()+"  当前角色法力值："+getMP()+"  HP药剂数量："+getHPdrug()+"  MP药剂数量："+getMPdrug());
	}
}
