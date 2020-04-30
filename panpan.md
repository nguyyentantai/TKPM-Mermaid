classDiagram
	class Customer
	Customer: custName: String
	Customer: custID: Int
	Customer: custPhnum: Int
	Customer: purchaseItem()
	Customer: requestBill()
	Customer: enterCustDetail()

	class PremiumCustomer
	PremiumCustomer: premiumDiscount: Int
	PremiumCustomer: enterCustDetail()

	class RegularCustomer
	RegularCustomer: regularDiscount: Int
	RegularCustomer: enterCustDetail()

	class Product
	Product: productID: Int
	Product: productName: String
	Product: productPrice: Float
	Product: getPrice()
	Product: setPrice()

	class Address
	Address: street: String
	Address: city: String
	Address: zipcode: Int
	Address: enterStreet()
	Address: enterCity()
	Address: enterState()
	Address: enterZipcode()

	class PurchaseDetail
	PurchaseDetail: custID: Int
	PurchaseDetail: quantity: Int
	PurchaseDetail: purchaseDate: Date
	PurchaseDetail: productID: Int
	PurchaseDetail: calculateTotalAmt()
	PurchaseDetail: generatePurchaseList()

	class Discount
	Discount: discountType
	Discount: discountValue
	Discount: SelectDiscount()

	class Bill
	Bill: payableAmt
	Bill: calculatePayableAmt()
	Bill: generateBill()

	class Payment Counter
	<<interface>> Payment Counter
	Payment Counter: calculatePayableAmt()
	Payment Counter: generateBill()

	Address "1" --* "1" Customer: Has
	Customer "1" -- "*" Product: Purchases
	PremiumCustomer --|> Customer
	RegularCustomer --|> Customer
	Bill --o Customer: Belongs to
	Bill ..|> Payment Counter: Accepts
	Bill ..|> Discount
	Bill ..|> PurchaseDetail
	Discount ..|> PurchaseDetail
	Customer -- PurchaseDetail
	PurchaseDetail -- Product