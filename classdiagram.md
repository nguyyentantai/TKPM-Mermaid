classDiagram
    
	Address "1" --* "1" Customer: Has
	Customer "1" -- "*" Product: Purchases
	PremiumCustomer --|> Customer
	RegularCustomer --|> Customer
	Bill --o Customer: Belongs to
	Bill ..|> Payment Counter: Accepts
	Bill ..> Discount
	Bill ..> PurchaseDetail
	Discount ..> PurchaseDetail
	Customer -- PurchaseDetail
	PurchaseDetail -- Product
    
    Customer: custName: String
	Customer: custID: Int
	Customer: custPhnum: Int
	Customer: purchaseItem()
	Customer: requestBill()
	Customer: enterCustDetail()
    
    PremiumCustomer: premiumDiscount: Int
	PremiumCustomer: enterCustDetail()

    RegularCustomer: regularDiscount: Int
	RegularCustomer: enterCustDetail()
    
    Product: productID: Int
	Product: productName: String
	Product: productPrice: Float
	Product: getPrice()
	Product: setPrice()
    
    Address: street: String
	Address: city: String
	Address: zipcode: Int
	Address: enterStreet()
	Address: enterCity()
	Address: enterState()
	Address: enterZipcode()
    
    PurchaseDetail: custID: Int
	PurchaseDetail: quantity: Int
	PurchaseDetail: purchaseDate: Date
	PurchaseDetail: productID: Int
	PurchaseDetail: calculateTotalAmt()
	PurchaseDetail: generatePurchaseList()
    
    Discount: discountType
	Discount: discountValue
	Discount: SelectDiscount()
    
    Bill: payableAmt
	Bill: calculatePayableAmt()
	Bill: generateBill()
    
    
    
    <<interface>> Payment Counter
	Payment Counter: calculatePayableAmt()
	Payment Counter: generateBill()