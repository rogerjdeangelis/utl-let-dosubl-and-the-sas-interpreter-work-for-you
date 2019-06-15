# utl-let-dosubl-and-the-sas-interpreter-work-for-you
Let dosubl and the sas interpreter work for you 

    Let dosubl and the sas interpreter work for you                                              
                                                                                                 
    github                                                                                       
    https://tinyurl.com/y3b7hmpk                                                                 
    https://github.com/rogerjdeangelis/utl-let-dosubl-and-the-sas-interpreter-work-for-you       
                                                                                                 
    SAS-L                                                                                        
    https://listserv.uga.edu/cgi-bin/wa?A2=SAS-L;4b571f01.1906c                                  
                                                                                                 
    *_                   _                                                                       
    (_)_ __  _ __  _   _| |_                                                                     
    | | '_ \| '_ \| | | | __|                                                                    
    | | | | | |_) | |_| | |_                                                                     
    |_|_| |_| .__/ \__,_|\__|                                                                    
            |_|                                                                                  
    ;                                                                                            
                                                                                                 
    cards4;                                                                                      
    1,2,5-7,8                                                                                    
    1-4,5,7                                                                                      
    1-5                                                                                          
    ;;;;                                                                                         
    run;quit;                                                                                    
    *                                                                                            
     _ __  _ __ ___   ___ ___  ___ ___                                                           
    | '_ \| '__/ _ \ / __/ _ \/ __/ __|                                                          
    | |_) | | | (_) | (_|  __/\__ \__ \                                                          
    | .__/|_|  \___/ \___\___||___/___/                                                          
    |_|                                                                                          
    ;                                                                                            
                                                                                                 
    %symdel txt / nowarn;                                                                        
    data _null_;                                                                                 
                                                                                                 
      input txt $80.;                                                                            
                                                                                                 
      txt=tranwrd(txt,"-"," to ");                                                               
      call symputx("txt",txt);                                                                   
                                                                                                 
      rc=dosubl('                                                                                
         %put &=txt;                                                                             
         data _null_;                                                                            
            do i = &txt;                                                                         
               put i @@;                                                                         
            end;                                                                                 
         run;quit;                                                                               
      ');                                                                                        
    cards4;                                                                                      
    1,2,5-7,8                                                                                    
    1-4,5,7                                                                                      
    1-5                                                                                          
    ;;;;                                                                                         
    run;quit;                                                                                    
                                                                                                 
    run;quit;                                                                                    
                                                                                                 
    *            _               _                                                               
      ___  _   _| |_ _ __  _   _| |_                                                             
     / _ \| | | | __| '_ \| | | | __|                                                            
    | (_) | |_| | |_| |_) | |_| | |_                                                             
     \___/ \__,_|\__| .__/ \__,_|\__|                                                            
                    |_|                                                                          
    ;                                                                                            
                                                                                                 
    OUTPUT (in the log)                                                                          
                                                                                                 
    1 2 5 6 7 8                                                                                  
    1 2 3 4 5 7                                                                                  
    1 2 3 4 5                                                                                    
                                                                                                 
