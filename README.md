# IncrementDecrement1

import java.awt.*;
import javax.swing.*;
import java.awt.event.*;
import java.awt.font.*;
import javax.swing.JFrame;

public class PushCounter {

	
	//creates and displays the main program frame
	public static void main(String[] args) {
		JFrame frame = new JFrame("Increment and Decrement");
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		
		IncrementDecrementPanel panel = new IncrementDecrementPanel();
		frame.getContentPane().add(panel);
		//frame.getContentPane().add(IncrementDecrementPanel());
		
		frame.pack();
		frame.setVisible(true);
		
		
		JFrame frame2 = new JFrame("Random Incrementer");
		frame2.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame2.pack();
		frame2.setVisible(true);
		

	}
}
	
	 class IncrementDecrementPanel extends JPanel {
		private int count;
		private JButton increment, decrement;
		private JLabel label;
		private JPanel buttonPanel;
		
		public IncrementDecrementPanel() {
			count = 50;
			
			increment = new JButton("increment");
			decrement = new JButton("decrement");
			
			ButtonListener listener = new ButtonListener();
			increment.addActionListener(listener);
			decrement.addActionListener(listener);
			
			label = new JLabel("Starting value: 50. add or subtract from this value.");
			buttonPanel = new JPanel();
			buttonPanel.setPreferredSize(new Dimension(100, 100));
			buttonPanel.setBackground(Color.red);
			buttonPanel.add(increment);
			buttonPanel.add(decrement);
			
			setPreferredSize(new Dimension(100, 100));
			setBackground(Color.pink);
			add(label);
			add(buttonPanel);
			
			//have not yet added whatever the fuck is a jframe frame
		
			JFrame frame = new JFrame("testing example");
			frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
			//frame.getContentPane().add(new StyleOptionsPanel());
			frame.pack();
			frame.setVisible(true);
		
		}
	
		class ButtonListener implements ActionListener {
		
		public void actionPerformed(ActionEvent event) {
			if (event.getSource() == increment) {
				count++;
				label.setText("add one");
				
				label.setText("value: " + count);
				count++;
		} else 
				label.setText("subtract one");
				count--;
				label.setText("value: " + count);
			
		}
	}
