package cse;

import java.awt.Checkbox;
import java.awt.CheckboxGroup;
import java.awt.Color;
import java.awt.FlowLayout;
import java.awt.Font;
import java.awt.GridLayout;
import java.awt.event.ItemEvent;
import java.awt.event.ItemListener;

import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;

public class TrafficLightSimulator extends JFrame implements ItemListener
{
	JLabel lb1,lb2;
	JPanel npPanel,cpPanel;
	CheckboxGroup cbg;
	public TrafficLightSimulator()
	{
		setVisible(true);
		setSize(600,400);
		setTitle("Traffic LIght Simulator");
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		
		setLayout(new GridLayout(2, 1));
		
		npPanel=new JPanel(new FlowLayout());
		cpPanel=new JPanel(new FlowLayout());
		
		lb1=new JLabel();
		Font font=new Font("Verdana",Font.BOLD, 70);
		lb1.setFont(font);
		npPanel.add(lb1);
		add(npPanel);
		Font fontR=new Font("Verdana",Font.BOLD,20);
		
		lb2=new JLabel("Select Lights");
		lb2.setFont(fontR);
		cpPanel.add(lb2);
		
		cbg=new CheckboxGroup();
		Checkbox rbn1=new Checkbox("Red Light",cbg,false);
		rbn1.setBackground(Color.RED);
		rbn1.setFont(fontR);
		cpPanel.add(rbn1);
		rbn1.addItemListener(this);
		
		Checkbox rbn2=new Checkbox("Orange Light",cbg,false);
		rbn2.setBackground(Color.ORANGE);
		rbn2.setFont(fontR);
		cpPanel.add(rbn2);
		rbn2.addItemListener(this);
		
		Checkbox rbn3=new Checkbox("Green Light",cbg,false);
		rbn3.setBackground(Color.GREEN);
		rbn3.setFont(fontR);
		cpPanel.add(rbn3);
		rbn3.addItemListener(this);
		
		add(cpPanel);
	}
		public void itemStateChanged(ItemEvent i)
		{
			Checkbox chk=cbg.getSelectedCheckbox();
			String str=chk.getLabel();
			char choice=str.charAt(0);
			switch (choice) 
			{
			case 'R':lb1.setText("STOP");
			lb1.setForeground(Color.RED);
		break;
				
			case 'O':lb1.setText("READY");
			lb1.setForeground(Color.ORANGE);
				break;
				
			case 'G':lb1.setText("GO");
				lb1.setForeground(Color.GREEN);
				

			
				break;
			}
		}
	public static void main(String[] args) 
	{
		new TrafficLightSimulator();

	}

}
