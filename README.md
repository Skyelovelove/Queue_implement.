# Queue_implement.
Implementation_of_queue
class Queue:
    def __init__(self,size):
        self.size=size
        self.top1=1
        self.top2=1
        self.s1=[0]*size
        self.s2=[0]*size
        self.count=0
    def rear(self,data):
        if(self.top1==self.top2==-1):
            self.top1=self.top2=0
        else:
            self.s1[self.top1]=data
            self.top1+=1
            self.count+=1
    def front(self):
        if(self.top1==self.top2==0):
            print(" EMPTY")
        else:
            for i in range(self.count):
                t1=self.s1.pop()
                self.s2[self.top2]=t1
                self.top2+=1
            b=self.s2.pop()
            self.count-=1
            self.top1-=1
            for i in range(self.count):
                t2=self.s2.pop()
                self.s1[i]=t2
    def display(self):
        try:
            #top1 is the topmost element index
            for i in range(self.top1+1):
                print(self.s1[i])
        except:pass
k=Queue(5)
k.rear(90)
k.rear(56)
k.rear(123)
k.front()
print(k.count,k.top1)
k.display()
