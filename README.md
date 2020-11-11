# mail_identifier
this code identifies a mail_Id , and do remove duplicates also gives as a string by just copying it and pasting it in mail TO or BCC space.
import pandas as pd
import re

def emilid_separating(item,stri):
    for i in item:
        if(type(i)!= float):
            searchObj= re.findall("([a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+)", i)
            for mail in searchObj:
                if mail not in auxiliaryList:
                    auxiliaryList.append(mail)
    
    
    for i in auxiliaryList:
    
        if stri == " ":
            stri=stri+i
        else:
            stri=stri+';'+i
    return(stri)
    
    

if __name__ == '__main__':
    
    filename="C:/Users/sravik158/Desktop/App_List.csv"
    df = pd.read_csv(filename)

    HOSTS=list(df['HOSTS'])
    L3Manager=list(df['L3 Manager'])
    #print(L3Manager)
    SecurityPOC=list(df['Security POC'])
    #print(SecurityPOC)
    APPdistro=list(df['APP Support Email Distro'])
    #print(APPdistro)
    #print("***********************************************")
    auxiliaryList = []
    stri = " "
    stri=emilid_separating(L3Manager,stri)
    stri=emilid_separating(SecurityPOC,stri)
    stri=emilid_separating(APPdistro,stri)
    print(stri)
    


    

        
    
            
            
                    
                
