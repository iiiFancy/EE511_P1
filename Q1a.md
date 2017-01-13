# EE511_P1
Project #1-Coin Flips
function x=fair_coin 
heads=0;
for i=1:50
    if (rand()>0.5)
        heads=heads+1;   
    end
end
x=heads;



function Proj1_1a
N=input('Please input the number of repeat');
NumberofHeads=zeros(1,N);
for i=1:N
   NumberofHeads(1,i)=fair_coin;
end
y=NumberofHeads;
x=(1:N);
bar(x,y);
