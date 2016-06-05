
import java.io.Serializable;

/**
 * 定义狂战士职业类	Berserker
 * @date 2016.5.31~2016.6.1
 * @author ZTW
 * @version 1.0
 * 狂战士职业的属性成长属于血少攻高防御低法力值也较低
 */
public class Berserker extends Professional implements Serializable
{
	@Override
	void addMaxHP(int lev) //定义狂战士职业的最大生命值成长公式
	{
		maxHP=10*(lev+4);
	}

	@Override
	void addMaxMP(int lev) //定义狂战士职业的最大法力值成长公式
	{
		maxMP=5*(lev+5);
	}

	@Override
	void addAttack(int lev)//定义狂战士职业的攻击成长公式
	{
		attack=attack+5;
	}

	@Override
	void addDefense(int lev) //定义狂战士职业的防御成长公式
	{
		defense=defense+3;
	}
}
