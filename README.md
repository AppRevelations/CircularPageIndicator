CircularPageIndicator
=====================
Create CircularPageIndicator using Fragments and Viewpager. Also you can swipe between fragments as it is the functionality of 
Viewpager which is not possible when use TabHost.With change in fragment indicator colour changes,in this project we made
three fragments and each one have its own indicator(cirular).You can change shape of indicator according to you if you want
square indicator then you have to change code in xml file(circle.xml and circle2.xml) in drawable folder.

MainActivity.java

Setting a PageChangeListener on ViewPager.

viewPager.setOnPageChangeListener(new ViewPager.OnPageChangeListener() {

            @Override
            public void onPageSelected(int position) {

           //what will happen on change of page is in function btnAction
             
                 btnAction(position);
            }

            @Override
            public void onPageScrolled(int arg0, float arg1, int arg2) {
            }

            @Override
            public void onPageScrollStateChanged(int arg0) {
            }
        });

    
  //changes color of page selected except of other pages
  
     private void btnAction(int action){
        
        switch(action)
        {
                  case 0:
                     
                      setButton(bt2,4,15,R.drawable.circle2);
                      setButton(bt1,4,15,R.drawable.circle);
                      setButton(bt3,4,15,R.drawable.circle);
                            break;
                  case 1: 
                      
                      setButton(bt1,4,15,R.drawable.circle2);
                      setButton(bt2,4,15,R.drawable.circle);
                      setButton(bt3,4,15,R.drawable.circle);
                            break;

                  case 2: 
                      setButton(bt3,4,15,R.drawable.circle2);
                      setButton(bt2,4,15,R.drawable.circle);
                      setButton(bt1,4,15,R.drawable.circle);
                            break;
        }
        
                                      }

        private void setButton(Button btn,int w,int h,int c)
        {
                btn.setWidth(w);
                btn.setHeight(h);
                btn.setBackgroundResource(c);
        }

