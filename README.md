# test1
#include<stdio.h>
main(){	
	printf("Hello World\n");
}							

//第二题
#include<stdio.h>
int main()
{
  int a[5],b[5][5];
  int i,j,sum,max,m,n;
  printf("输入5个整数\n");
  for(i=0;i<5;i++)
    scanf("%d",&a[i]);//输入数据
  for(i=0;i<5;i++)
  {
    sum=0;
    for(j=i;j<5;j++)//从第一位开始往后相加求和
    {
      sum+=a[j];
      b[i][j]=sum;//保存到二维数组中
    }
  }
  max=b[0][0];
  for(i=0;i<5;i++)//比较二维数组找到里面的最大值
  {
    for(j=i;j<5;j++)
    {
      if(b[i][j]>max)
      {
        max=b[i][j];
        m=i+1;//记录最大值的位置
        n=j+1;
      }
    }
  }
  printf("最大值和为:%d   他是从第%d 加到第%d 位的和\n",max,m,n); 
  return 0;
}


//第三题
#include<stdio.h>
  int main(){
  char sentence[100];
  int len=0,j,wordlen=0;
  gets(sentence);
  while(sentence[len]) len++;
for(j=len-1;j>=0;j--){
	if(sentence[j]>='a'&&sentence[j]<='z'||sentence[j]>='A'&&sentence[j]<='Z')
{
	wordlen++;
}
else if(wordlen>0){
	printf("%*.*s",wordlen,wordlen,&sentence[j+1]);
	printf("%c",sentence[j]);
	wordlen=0;
}
else
	rintf("%c",sentence[j]);
}
if(wordlen>0) 
	printf("%*.*s",wordlen,wordlen,sentence);
	return 0;
/*
 * 在主窗口显示"Hello World"，并能用鼠标拖动
 * @author  SJ
 */
import java.awt.Color;
import java.awt.Font;
import java.awt.Graphics;
import java.awt.Graphics2D;
import java.awt.event.MouseEvent;
import java.awt.event.MouseMotionListener;

import javax.swing.JFrame;
import javax.swing.JPanel;

public class Demo04 {
	private int x = 100;
	private int y = 250;

	public void ShowJframe() {
		JFrame jframe = new JFrame("移动的文字");
		@SuppressWarnings("serial")
		final JPanel jpanel = new JPanel() {
			public void paint(Graphics g) {
				Graphics2D graphics = (Graphics2D) g;
				graphics.setColor(Color.white);
				graphics.fillRect(0, 0, 400, 500);
				graphics.setFont(new Font("黑体", Font.BOLD, 20));
				graphics.setColor(Color.red);
				graphics.drawString("Hello World", x, y);
			}
		};
		jpanel.addMouseMotionListener(new MouseMotionListener() {

			@Override
			public void mouseMoved(MouseEvent e) {
			}

			@Override
			public void mouseDragged(MouseEvent e) {
				x = e.getX();
				y = e.getY();
				jpanel.repaint();

			}
		});
		jframe.add(jpanel);
		jframe.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		jframe.setBounds(200, 300, 400, 500);
		jframe.setVisible(true);
	}

	public static void main(String[] args) {
		new Demo04().ShowJframe();
	}

}
