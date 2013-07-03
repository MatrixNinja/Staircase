/*
Staircase
=========
Build a staircase with colors dividing them in half,
odd numbers will result in the lower colored half having the extra stair.
*/


package com.egarduno.staircase;
import java.awt.Color;
import acm.graphics.*;
import acm.program.*;
import acm.io.*;
import acm.io.IODialog;

/*__________________________________

ITC 115 - Emilio Garduno - 07/03/2013
Assignment 2 - Staircase
__________________________________*/


public class A2Staircase extends GraphicsProgram{
    
  int stairs;
	GRect rect;
	
	
	public void run(){
		this.getParent().getParent().setBounds(300,100,800,800); //(from left,from top,width,height)
		IODialog q= new IODialog();
		stairs=q.readInt("Enter the number of stairs you want to create:");
		MakeRectangles();
	}
	
	
/*____________METHODS____________*/
	private void MakeRectangles(){
		int x = 0;
		int y = 0;
		
		for (int s=1; s <= stairs; s++){
			rect = new GRect(x,y, 100, 50);
			if(s <= stairs/2){
				rect.setColor(Color.BLUE);
				rect.setFillColor(Color.RED);
				rect.setFilled(true);
			}
			else {
				rect.setColor(Color.RED);
				rect.setFillColor(Color.BLUE);
				rect.setFilled(true);				
			}
			
			add(rect);
			x +=70;
			y +=50;
		}
	}
}
