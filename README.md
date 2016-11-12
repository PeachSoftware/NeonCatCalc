ode der einen datei:







package run;

import javax.swing.JFrame;

public class Start {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		JFrame frame = new   JFrame("Calc");
		frame.setSize(800, 600);
		frame.setLayout(null);
		frame.setLocationRelativeTo(null);
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setResizable(false);
				
		
		CalcPanel cp = new CalcPanel();
		cp.setBounds(0,0,800,600);
		
		frame.add(cp);
		frame.setVisible(true);
		
	}

}











code der anderen datei:





package run;

import java.awt.Color;
import java.awt.Font;
import java.awt.Insets;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.AbstractButton;
import javax.swing.JButton;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JTextField;

public class CalcPanel extends JPanel {
	float a = 0;
	float b = 0;
	public CalcPanel(){
		
		setLayout(null);
		setSize(800, 600);
		setBackground(Color.MAGENTA);
	
		Font schrift = new Font("Arial",Font.PLAIN,35);
		
		
		
		JTextField textfeld = new JTextField();
		textfeld.setBounds(200, 200, 100, 30);
		JTextField textfeld2 = new JTextField();
		textfeld2.setBounds(410, 200, 100, 30);
		JLabel textlabel = new JLabel("Statt Komma bitte Punkt eingeben");
		textlabel.setBounds(2, 550, 200, 30);
		JLabel textlabel2 = new JLabel ("+");
		textlabel2.setBounds(350, 200, 100, 30);
		textlabel2.setFont(schrift);
		JLabel textlabel3 = new JLabel("1.zahl");
		textlabel3.setBounds(250, 160, 100, 30);
		JLabel textlabel4 = new JLabel ("2.zahl");
		textlabel4.setBounds(450 , 160, 100 , 30);
		JLabel textlabel5 = new JLabel("");
		textlabel5.setBounds(305,470,300,45);
		textlabel5.setFont(schrift);
		
		JButton plus = new JButton("+");
		plus.setBounds(300, 250, 45, 45);
		plus.setMargin(new Insets(1,1,1,1));
		plus.setFont(schrift);
		
		plus.addActionListener(new ActionListener ()	{
			public void actionPerformed(ActionEvent ae)		{
				textlabel2.setText("+");
				textfeld.setEnabled(true);
				textfeld2.setEnabled(true);
				textfeld.setBackground(Color.WHITE);
				textfeld2.setBackground(Color.WHITE);
			}
		});
		
		JButton minus = new JButton("-");
		minus.setBounds(365, 250, 45, 45);
		minus.setMargin(new Insets(1,1,1,1));
		minus.setFont(schrift);;
		

		minus.addActionListener(new ActionListener ()	{
			public void actionPerformed(ActionEvent ae)		{
				textlabel2.setText("-");
				textfeld.setEnabled(true);
				textfeld2.setEnabled(true);
				textfeld.setBackground(Color.WHITE);
				textfeld2.setBackground(Color.WHITE);
			}
		});
		
		JButton mal = new JButton("x");
		mal.setBounds(300, 305, 45, 45);
		mal.setMargin(new Insets(1,1,1,1));
		mal.setFont(schrift);
		

		mal.addActionListener(new ActionListener ()	{
			public void actionPerformed(ActionEvent ae)		{
				textlabel2.setText("X");
				textfeld.setEnabled(true);
				textfeld2.setEnabled(true);
				textfeld.setBackground(Color.WHITE);
				textfeld2.setBackground(Color.WHITE);
			}
		});
		
		JButton geteilt = new JButton(":");
		geteilt.setBounds(365, 305, 45, 45);
		geteilt.setMargin(new Insets(1,1,1,1));
		geteilt.setFont(schrift);

		geteilt.addActionListener(new ActionListener ()	{
			public void actionPerformed(ActionEvent ae)		{
				textlabel2.setText(":");
				textfeld.setEnabled(true);
				textfeld2.setEnabled(true);
				textfeld.setBackground(Color.WHITE);
				textfeld2.setBackground(Color.WHITE);
			}
		});
		
		
		JButton wurzel = new JButton("\u221A");
		wurzel.setBounds(300, 360, 45, 45);
		wurzel.setMargin(new Insets(1,1,1,1));
		wurzel.setFont(schrift);

		wurzel.addActionListener(new ActionListener ()	{
			public void actionPerformed(ActionEvent ae)		{
				textlabel2.setText("\u221A");
				textfeld.setEnabled(false);
				textfeld2.setEnabled(true);
				textfeld.setBackground(Color.BLACK);
				textfeld2.setBackground(Color.WHITE);
				textfeld.setText("");
			}
		});
		
		JButton quadrat = new JButton("x\u00B2");
		quadrat.setBounds(365, 360, 45, 45);
		quadrat.setMargin(new Insets(1,1,1,1));
		quadrat.setFont(schrift);

		quadrat.addActionListener(new ActionListener ()	{
			public void actionPerformed(ActionEvent ae)		{
				textlabel2.setText("x\u00B2");
				textfeld.setEnabled(true);
				textfeld2.setEnabled(false);
				textfeld.setBackground(Color.WHITE);
				textfeld2.setBackground(Color.BLACK);
				textfeld2.setText("");
			}
		});
		
		
		JButton gleich = new JButton("=");
		gleich.setBounds(305, 415, 100, 45);
		gleich.setMargin(new Insets(1,1,1,1));
		gleich.setFont(schrift);
		gleich.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {
		
				float zwischenspeicher = 0;
				try{
				 a = Float.parseFloat(textfeld.getText());
				 b = Float.parseFloat(textfeld2.getText());
				
				if (textlabel2.getText().equals("+")){
					zwischenspeicher = a+b;
					textlabel5.setText(zwischenspeicher+"");
				}
				if (textlabel2.getText().equals("-")){
					 zwischenspeicher = a-b;
					 textlabel5.setText(zwischenspeicher+"");
					 
				}
				if (textlabel2.getText().equals("X")){
					 zwischenspeicher = a*b;
					 textlabel5.setText(zwischenspeicher+"");
				}
				if (textlabel2.getText().equals(":")){
					 zwischenspeicher = a/b;
					 textlabel5.setText(zwischenspeicher+"");
				}	 
				if (textlabel2.getText().equals("\u221A")){
					 zwischenspeicher = (float) Math.sqrt(b);	 
					 textlabel5.setText(zwischenspeicher+"");
				}
				if (textlabel2.getText().equals("x\u00B2")){
					 zwischenspeicher = (float) Math.pow(a,2);
					 textlabel5.setText(zwischenspeicher+"");
				}
				
				}catch(NumberFormatException nfe) {
					textlabel5.setText("Keine Zahl !");
				}
					
					
				}
			
		});
		
			
				
					
	

	add (textfeld);
	add (textfeld2);
	add (textlabel);
	add (textlabel2);
	add (textlabel3);
	add (textlabel4);
	add (textlabel5);
	add (plus);
	add (minus);
	add (mal);
	add (geteilt);
	add (wurzel);
	add (quadrat);
	add(gleich);
	
	}
}
