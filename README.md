# BRN AutoTx

A Python script that automates the transfer of BRN tokens to multiple recipient addresses on the BRN network. The script reads addresses from `addresses.txt`, selects a random transfer amount within a user-defined range, and sends transactions with detailed logging and confirmation.

## Features

- **Automated Transfers:** Sends BRN tokens to all recipient addresses listed in `addresses.txt`.
- **Randomized Amounts:** Transfers a random amount (within a specified range) for each transaction.
- **Dynamic Gas Estimation:** Uses on-chain gas estimation with a fallback value if estimation fails.
- **Retry Mechanism:** Retries failed transactions up to a configurable number of attempts.
- **Color-Coded Logging:** Provides clear, color-coded output for easy monitoring.
- **Faucet:** Need test BRN tokens? Use the [BRN Faucet](https://faucet.brn.t3rn.io/).

## Installation

### 1. Clone the Repository
```bash
git clone https://github.com/kelliark/Brn-AutoTx.git
cd Brn-AutoTx
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

## Configuration  

### **1. Set Up Your Environment**  
Before running the script, configure your private key in *config.py*

```bash
PRIVATE_KEY = "PRIVATEKEYADDRESSHERE"
```

### **2. Prepare `addresses.txt`**  
Add recipient addresses (one per line) in `addresses.txt`:  
```
0xRecipientAddress1
0xRecipientAddress2
0xRecipientAddress3
```

## Usage  

Run the script with:  
```bash
python main.py
```

You will be prompted to:  
1. Enter the **minimum and maximum** BRN amount for transfers  
2. Specify the **number of loops**  

The script will process each address from `addresses.txt`, select a random amount (within your defined range) for each, and send the transaction.

### Example Output
```
Found 3 recipient addresses.
Enter minimum amount: 0.0001
Enter maximum amount: 0.0001
Enter the number of loops: 100

INFO: Loop 1/100
INFO: Sending 0.00010000 BRN to 0x975****9A6F
Transaction sent! Hash: 0x85f10419033220b8dd28d27c63c71ba1cbb01f240aa7ebcd8a209ba89495d1cc
Transaction confirmed in block: 25371136
Gas Used: 38051
...
```

## BRN Faucet

If you need test BRN tokens for testing your transactions, you can obtain them from the [BRN Faucet](https://faucet.brn.t3rn.io/).

## License

This project is licensed under the MIT License.

## Disclaimer

This script interacts directly with your wallet. **Use at your own risk and never share your private key or other sensitive information publicly.**
