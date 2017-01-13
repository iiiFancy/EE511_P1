# EE511_P1
Project #1-Coin Flips
function flip_coin_n
%initialize, N is used to track the heads run length, HeadRunLength is used to store them.
P=input('Please input the probability of tails ');
T=input('Please input the experience times ');
tails=0;
heads=0;
N=0;
HeadRunLength=zeros(1,T);
i=1;
while(i<=T)
    if(rand()<=P)
        tails=tails+1;
        HeadRunLength(1,i)=N;   %when we get a tail, initialize N and store it before initialization
        N=0;                    
    else
        heads=heads+1;
        N=N+1;
    end
    i=i+1;
end
%display our final outcomes and histogram
LongestRun=max(HeadRunLength);
display('the number of tails'),display(tails);
display('the number of heads'),display(heads);
display('the number of longest run of heads'),display(LongestRun);
x=[0,1];
y=[tails,heads];
subplot(2,1,1),bar(x,y);    %histogram for the tails and heads
HeadRunLength(HeadRunLength==0)=[]; %eliminate zeros in the array
subplot(2,1,2),hist(HeadRunLength,(1:10));  %histogram for heads run length(the longest run mostly less than 10 )
