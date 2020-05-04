---
title: 'Project documentation template'
disqus: hackmd
---
Seminar \#1 - Mermaid
===
###### tags: ```TKPM-Mermaid```

## Cú pháp ```mermaid```

[https://mermaid-js.github.io/mermaid/#/](https://mermaid-js.github.io/mermaid/#/)

## Luyện tập

Sử dụng cú pháp `mermaid`, vẽ các diagram sau:

### Flow Chart

- Euclide GCD
- Quadratic Equation

### Class Diagram

```mermaid
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
    
    
    
    interface Payment Counter
	Payment Counter: calculatePayableAmt()
	Payment Counter: generateBill()

```

### Sequence Diagram

![](https://cdn.visual-paradigm.com/guide/uml/what-is-sequence-diagram/16-sequence-diagram-for-use-case.png)

### State Chart Diagram

[![](https://mermaid.ink/img/eyJjb2RlIjoic3RhdGVEaWFncmFtXG4gICAgXG4gICAgc3RhdGUgSWRsZXt9XG4gICAgXG4gICAgWypdIC0tPiBJZGxlXG4gICAgXG4gICAgc3RhdGUgQWNjb3VudEFjdGlvbnN7fVxuICAgIFxuICAgIHN0YXRlIERpc3BlbnNlTW9uZXl7fVxuICAgIFxuICAgIHN0YXRlIFByaW50UmVjZWlwdHt9XG4gICAgXG4gICAgc3RhdGUgVmVyaWZ5QWNjb3VudHtcbiAgICAgICAgc3RhdGUgVmVyaWZ5Q2FyZHtcbiAgICAgICAgICAgIGNhcmRTdWJtaXR0ZWRcbiAgICAgICAgICAgIHJlYWRDYXJkXG4gICAgICAgICAgICByZXR1cm5DYXJkXG4gICAgICAgIH1cbiAgICAgICAgc3RhdGUgQ2hlY2tDYXJkIDw8Zm9yaz4-XG4gICAgICAgIFZlcmlmeUNhcmQgLS0-IENoZWNrQ2FyZFxuICAgICAgICBDaGVja0NhcmQgLS0-IElkbGU6IGVsc2VcbiAgICAgICAgQ2hlY2tDYXJkIC0tPiBDYXJkVmFsaWQ6IFtjYXJkVmFsaWRdXG5cblx0XHRzdGF0ZSBDYXJkVmFsaWR7fVxuXG4gICAgICAgIENhcmRWYWxpZCAtLT4gVmVyaWZ5UGluXG4gICAgICAgIFxuXHRcdHN0YXRlIFZlcmlmeVBpbntcblx0XHRcdHBpblN1Ym1pdFxuXHRcdFx0Y2hlY2tQaW5cblx0XHRcdHJldHVybkNhcmRcblx0XHR9XG4gICAgICAgIHN0YXRlIENoZWNrUGluIDw8Zm9yaz4-XG4gICAgICAgIFZlcmlmeVBpbiAtLT4gQ2hlY2tQaW5cbiAgICAgICAgQ2hlY2tQaW4gLS0-IFBpbkNvcnJlY3QgOiBQSU52YWxpZFxuICAgICAgICBDaGVja1BpbiAtLT4gUGluSW5jb3JyZWN0IDogZWxzZVxuICAgICAgICBcblx0XHRzdGF0ZSBQaW5Db3JyZWN0e31cblxuXHRcdHN0YXRlIFBpbkluY29ycmVjdHt9XG4gICAgICAgIFBpbkluY29ycmVjdCAtLT4gQ2hlY2tQaW46IFt0cmllczxtYXhUcmllc10vdHJpZXMrK1xuICAgIH1cbiAgICBcbiAgICBBY2NvdW50QWN0aW9ucyAtLT4gRGlzcGVuc2VNb25leVxuICAgIFxuICAgIERpc3BlbnNlTW9uZXkgLS0-IFByaW50UmVjZWlwdFxuICAgIFxuICAgIFByaW50UmVjZWlwdCAtLT4gVHJhbnNhY3Rpb25Db21wbGV0ZVxuICAgIFxuICAgIEFjY291bnRBY3Rpb25zIC0tPiBQcmludFJlY2VpcHRcbiAgICBcbiAgICBEaXNwZW5zZU1vbmV5IC0tPiBUcmFuc2FjdGlvbkNvbXBsZXRlXG4gICAgXG4gICAgVHJhbnNhY3Rpb25Db21wbGV0ZSAtLT4gSWRsZVxuICAgIFxuICAgIElkbGUgLS0-IFZlcmlmeUFjY291bnRcblxuICAgIFxuIiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQifSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)](https://mermaid-js.github.io/mermaid-live-editor/#/edit/eyJjb2RlIjoic3RhdGVEaWFncmFtXG4gICAgXG4gICAgc3RhdGUgSWRsZXt9XG4gICAgXG4gICAgWypdIC0tPiBJZGxlXG4gICAgXG4gICAgc3RhdGUgQWNjb3VudEFjdGlvbnN7fVxuICAgIFxuICAgIHN0YXRlIERpc3BlbnNlTW9uZXl7fVxuICAgIFxuICAgIHN0YXRlIFByaW50UmVjZWlwdHt9XG4gICAgXG4gICAgc3RhdGUgVmVyaWZ5QWNjb3VudHtcbiAgICAgICAgc3RhdGUgVmVyaWZ5Q2FyZHtcbiAgICAgICAgICAgIGNhcmRTdWJtaXR0ZWRcbiAgICAgICAgICAgIHJlYWRDYXJkXG4gICAgICAgICAgICByZXR1cm5DYXJkXG4gICAgICAgIH1cbiAgICAgICAgc3RhdGUgQ2hlY2tDYXJkIDw8Zm9yaz4-XG4gICAgICAgIFZlcmlmeUNhcmQgLS0-IENoZWNrQ2FyZFxuICAgICAgICBDaGVja0NhcmQgLS0-IElkbGU6IGVsc2VcbiAgICAgICAgQ2hlY2tDYXJkIC0tPiBDYXJkVmFsaWQ6IFtjYXJkVmFsaWRdXG5cblx0XHRzdGF0ZSBDYXJkVmFsaWR7fVxuXG4gICAgICAgIENhcmRWYWxpZCAtLT4gVmVyaWZ5UGluXG4gICAgICAgIFxuXHRcdHN0YXRlIFZlcmlmeVBpbntcblx0XHRcdHBpblN1Ym1pdFxuXHRcdFx0Y2hlY2tQaW5cblx0XHRcdHJldHVybkNhcmRcblx0XHR9XG4gICAgICAgIHN0YXRlIENoZWNrUGluIDw8Zm9yaz4-XG4gICAgICAgIFZlcmlmeVBpbiAtLT4gQ2hlY2tQaW5cbiAgICAgICAgQ2hlY2tQaW4gLS0-IFBpbkNvcnJlY3QgOiBQSU52YWxpZFxuICAgICAgICBDaGVja1BpbiAtLT4gUGluSW5jb3JyZWN0IDogZWxzZVxuICAgICAgICBcblx0XHRzdGF0ZSBQaW5Db3JyZWN0e31cblxuXHRcdHN0YXRlIFBpbkluY29ycmVjdHt9XG4gICAgICAgIFBpbkluY29ycmVjdCAtLT4gQ2hlY2tQaW46IFt0cmllczxtYXhUcmllc10vdHJpZXMrK1xuICAgIH1cbiAgICBcbiAgICBBY2NvdW50QWN0aW9ucyAtLT4gRGlzcGVuc2VNb25leVxuICAgIFxuICAgIERpc3BlbnNlTW9uZXkgLS0-IFByaW50UmVjZWlwdFxuICAgIFxuICAgIFByaW50UmVjZWlwdCAtLT4gVHJhbnNhY3Rpb25Db21wbGV0ZVxuICAgIFxuICAgIEFjY291bnRBY3Rpb25zIC0tPiBQcmludFJlY2VpcHRcbiAgICBcbiAgICBEaXNwZW5zZU1vbmV5IC0tPiBUcmFuc2FjdGlvbkNvbXBsZXRlXG4gICAgXG4gICAgVHJhbnNhY3Rpb25Db21wbGV0ZSAtLT4gSWRsZVxuICAgIFxuICAgIElkbGUgLS0-IFZlcmlmeUFjY291bnRcblxuICAgIFxuIiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQifSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)




:::warning
**Bài làm nhóm**. Có thể dùng `Mermaid Live Editor` để thử nghiệm.
