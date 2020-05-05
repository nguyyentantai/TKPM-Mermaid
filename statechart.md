stateDiagram
    
    state Idle{}
    
    [*] --> Idle
    
    state AccountActions{}
    
    state DispenseMoney{}
    
    state PrintReceipt{}
    
    state VerifyAccount{
        state VerifyCard{
            cardSubmitted
            readCard
            returnCard
        }
        state CheckCard <<fork>>
        VerifyCard --> CheckCard
        CheckCard --> Idle: else
        CheckCard --> CardValid: [cardValid]

		state CardValid{}

        CardValid --> VerifyPin
        
		state VerifyPin{
			pinSubmit
			checkPin
			returnCard
		}
        state CheckPin <<fork>>
        VerifyPin --> CheckPin
        CheckPin --> PinCorrect : PINvalid
        CheckPin --> PinIncorrect : else
        
		state PinCorrect{}

		state PinIncorrect{}
        PinIncorrect --> CheckPin: [tries<maxTries]/tries++
    }
    
    AccountActions --> DispenseMoney
    
    DispenseMoney --> PrintReceipt
    
    PrintReceipt --> TransactionComplete
    
    AccountActions --> PrintReceipt
    
    DispenseMoney --> TransactionComplete
    
    TransactionComplete --> Idle
    
    Idle --> VerifyAccount