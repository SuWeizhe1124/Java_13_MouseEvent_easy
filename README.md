實作做一個視窗,與使用者點擊處標示一個黑點。 可藉由內嵌縮短程式碼
package learning.AWT;

import java.awt.*;
import java.awt.event.*;

public class Java_13_MouseEvent extends Frame{
    Java_13_MouseEvent(){
        this.setLocation(100,50);
        this.setTitle("Mouse Clicker");
        this.setSize(500,500);
        this.setVisible(true);
        this.setLayout(null);
        this.addWindowListener(new WindowAdapter() { //此處是使用內嵌類別委任視窗事件
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
        this.addMouseListener(new MouseAdapter() { //此處是使用內嵌類別委任滑鼠事件
            public void mouseClicked(MouseEvent e) {
                int x, y;
                Graphics g;
                g = getGraphics(); //取得繪圖物件
                x = e.getX();
                y = e.getY();
                g.fillRect(x, y, 10, 10); //設定點擊位置的方塊大小
                System.out.println(e.getButton()); //可取得點擊鍵
            }
        });
    }

    public static void main(String[] args) {
        Java_13_MouseEvent frm = new Java_13_MouseEvent();
    }
}
