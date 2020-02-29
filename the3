import sys

map1 = sys.argv[1]
rules = sys.argv[2]
generation = int(sys.argv[3])


map_list = []
rule_list = []


with open(map1,'r')as file_data:
    for line in file_data.readlines():
         map_list.append(line.strip())

with open(rules,'r')as file_data:
    for line in file_data.readlines():
         rule_list.append(line.strip())
row_lenght=len(map_list[0])
column_lenght=len(map_list)        
def neighbours_finder(map_list):
    neighbours=[]
    count=0
    if row_lenght==1 and column_lenght==1:
        neighbours=[0]      
        return neighbours  
    elif column_lenght==1:        
        for i in range(0,row_lenght):
            if i==0:
                if map_list[0][1]=='*':
                    count+=1
                neighbours.append(count)
                count=0
            if i!=0 and i!=row_lenght-1:
                if map_list[0][i-1]=='*':
                    count+=1
                if map_list[0][i+1]=='*':
                    count+=1
                neighbours.append(count)
                count=0
            if i==row_lenght-1:
                if map_list[0][i-1]=='*':
                    count+=1
                neighbours.append(count)
                count=0     
        return neighbours   
    elif row_lenght==1:
        for j in range(0,column_lenght):
            if j==0:
                if map_list[1][0]=='*':
                    count+=1
                neighbours.append(count)
                count=0
            if j!=0 and j!=column_lenght-1:
                if map_list[j-1][0]=='*':
                    count+=1
                if map_list[j+1][0]=='*':
                    count+=1
                neighbours.append(count)
                count=0
            if j==column_lenght-1:
                if map_list[j-1][0]=='*':
                    count+=1
                neighbours.append(count)
                count=0 
        return neighbours       
    else:
        for j in range(0,column_lenght):
            for i in range(0,row_lenght):
                if j==0 and i==0:
                    if map_list[0][1]=='*':
                        count+=1
                    if map_list[1][0]=='*':
                        count+=1
                    if map_list[1][1]=='*':
                        count+=1
                    neighbours.append(count)
                    count=0
                if j==0 and i!=0 and i!= row_lenght-1:
                    if map_list[j][i+1]=='*':
                        count+=1
                    if map_list[j][i-1]=='*':
                        count+=1
                    if map_list[j+1][i-1]=='*':
                        count+=1
                    if map_list[j+1][i]=='*':
                        count+=1
                    if map_list[j+1][i+1]=='*':
                        count+=1
                    neighbours.append(count)
                    count=0
                if j==0 and i== row_lenght-1:
                    if map_list[j][i-1]=='*':
                        count+=1
                    if map_list[j+1][i-1]=='*':
                        count+=1
                    if map_list[j+1][i]=='*':
                        count+=1
                    neighbours.append(count)
                    count=0
                if j!=0 and j!= column_lenght-1:
                    if i==0:
                        if map_list[j-1][0]=='*':
                            count+=1
                        if map_list[j-1][1]=='*':
                            count+=1
                        if map_list[j][1]=='*':
                            count+=1
                        if map_list[j+1][0]=='*':
                            count+=1
                        if map_list[j+1][1]=='*':
                            count+=1
                        neighbours.append(count)
                        count=0
                    if i!=0 and i!= row_lenght-1:
                        if map_list[j-1][i-1]=='*':
                            count+=1
                        if map_list[j-1][i]=='*':
                            count+=1
                        if map_list[j-1][i+1]=='*':
                            count+=1
                        if map_list[j][i-1]=='*':
                            count+=1
                        if map_list[j][i+1]=='*':
                            count+=1
                        if map_list[j+1][i-1]=='*':
                            count+=1
                        if map_list[j+1][i]=='*':
                            count+=1
                        if map_list[j+1][i+1]=='*':
                            count+=1
                        neighbours.append(count)
                        count=0
                    if i== row_lenght-1:
                        if map_list[j-1][i-1]=='*':
                            count+=1
                        if map_list[j-1][i]=='*':
                            count+=1
                        if map_list[j][i-1]=='*':
                            count+=1
                        if map_list[j+1][i-1]=='*':
                            count+=1
                        if map_list[j+1][i]=='*':
                            count+=1
                        neighbours.append(count)
                        count=0
                if j== column_lenght-1:
                    if i==0:
                        if map_list[j-1][i]=='*':
                            count+=1
                        if map_list[j-1][i+1]=='*':
                            count+=1
                        if map_list[j][i+1]=='*':
                            count+=1
                        neighbours.append(count)
                        count=0
                    if i!=0 and i!= row_lenght-1:
                        if map_list[j-1][i-1]=='*':
                            count+=1
                        if map_list[j-1][i]=='*':
                            count+=1
                        if map_list[j-1][i+1]=='*':
                            count+=1
                        if map_list[j][i-1]=='*':
                            count+=1
                        if map_list[j][i+1]=='*':
                            count+=1
                        neighbours.append(count)
                        count=0
                    if i== row_lenght-1:
                        if map_list[j-1][i-1]=='*':
                            count+=1
                        if map_list[j-1][i]=='*':
                            count+=1
                        if map_list[j][i-1]=='*':
                            count+=1
                        neighbours.append(count)
                        count=0
        return neighbours
x=neighbours_finder(map_list)

def new_map():
    global map_list
    for j in range(0,column_lenght):
        for i in range(0,row_lenght):
            for a,b,c,d in rule_list:
                
                if a!=d and a==map_list[j][i]:
                    if b=='<' and x[j*row_lenght+i]<int(c):
                        
                        map_list[j]=list(map_list[j])                                            
                        map_list[j][i]=d
                        map_list[j]=''.join(map_list[j])
                        break
                    elif b=='=' and x[j*row_lenght+i]==int(c):                        
                        map_list[j]=list(map_list[j])
                        map_list[j][i]=d
                        map_list[j]=''.join(map_list[j])
                        break
                    elif b=='>' and x[j*row_lenght+i]>int(c):
                        
                        map_list[j]=list(map_list[j])
                        map_list[j][i]=d
                        map_list[j]=''.join(map_list[j])
                        break
gen=0
while gen<generation:
    new_map()
    x=neighbours_finder(map_list)
    gen+=1
for i in map_list:
    print i
