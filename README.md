class expense_tracker:
    def __init__(self,loan,grocery,medical,monthlybill):
        self.revenue=15000
        self.loan=loan 
        self.grocery=grocery
        self.medical=medical
        self.monthlybill=monthlybill
        self.depo_bal=0
        self.balance=0
      
    def monthly_revenue(self):
        print("monthly revenue:",self.revenue)
    def balance1(self):
        if self.revenue>0:
            self.balance=self.revenue-self.loan-self.grocery-self.medical-self.monthlybill
            print("balance:",self.balance)
    def expense_limiter(self):
        limit=int(input("enter expense limit % :"))
        print("reached the limit:",(self.revenue*limit/100))
        if self.balance>self.revenue*20/100:
            print("you have saved ",self.balance-self.revenue*20/100,"above the limit")
    def additional_exp(self):
        global exp
        exp=int(input("enter additional expense amount :"))
        self.balance=self.revenue-self.loan-self.grocery-self.medical-self.monthlybill-exp
        print("balance after additional expense",self.balance)
    def deposit(self):
        if self.balance>0:
            self.depo_bal=self.depo_bal+self.balance
            print("your deposit balance:",self.depo_bal)
        else:
            print('unavailable balance')
    def catagory_with_more_exp(self):
        if self.grocery>self.medical and self.grocery>self.monthlybill:
            print("grocery cause more expense")
        elif self.medical>self.grocery and self.medical>self.monthlybill:
            print("medical cause more expense")
        else:
            print("monthlybill cause more expense")
        

