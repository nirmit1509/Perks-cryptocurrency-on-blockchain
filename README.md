# Perks-cryptocurrency-on-blockchain
This cryptocurrency is implemented on BlockChain in python.
Flask framework is used for  building web applications.
Postman used to make requests.

Features:
1. You can make transactions between nodes.
2. Consensus Protocol is achieved.
3. Mine a new block and get rewarded with some Perks.
4. Get full blockchain transactions till date.


PROJECT FLOW

1. First of all start 3 different nodes on different ports i.e. 5001, 5002 and 5003.

2. Initialize all nodes with a genesis block using GET request on function "get_chain()".

![image](https://user-images.githubusercontent.com/55524764/95602609-c6a23200-0a72-11eb-9784-fd635dfdbc2a.png)

3. Repeat the same process for all the other 2 nodes.

4. Connect all the nodes together using POST request with specified json format on function "connect_node()".

![image](https://user-images.githubusercontent.com/55524764/95602631-cefa6d00-0a72-11eb-8d1d-45292e9641b6.png)

5. After all nodes are connected, we start mining the blocks using function "mine_node()". You will receive an award of 10 perks once block is successfully mined.

![image](https://user-images.githubusercontent.com/55524764/95603559-146b6a00-0a74-11eb-9d85-859471999f55.png)

6. Now fetch the latest chain with new mined block using GET request on function "get_chain()".

![image](https://user-images.githubusercontent.com/55524764/95603583-1af9e180-0a74-11eb-93df-9e63d2c2ccf8.png)

7. In this step, replace the chain with latest chain on port 5002. We achieve this using "replace_chain()" method.

![image](https://user-images.githubusercontent.com/55524764/95603661-349b2900-0a74-11eb-8f0f-c1aec5848b2d.png)

8. Repeat the same step on port 5003 in order to achieve the consensus on all the 3 different nodes.

9. Now we will transfer 100 perks from node 5001 to 5002 by adding a transaction using POST method on "add_transaction()". Add the sender details, receiver details and amount to transfer using json format.

![image](https://user-images.githubusercontent.com/55524764/95603684-3d8bfa80-0a74-11eb-8f3c-d1ad713661b9.png)

10. Again mine this transaction in order to add this in the chain.

![image](https://user-images.githubusercontent.com/55524764/95603706-454b9f00-0a74-11eb-97d9-24d944f85a19.png)

11. Now fetch this updated chain on node 5001 using "get_chain()" method.

![image](https://user-images.githubusercontent.com/55524764/95603730-4d0b4380-0a74-11eb-9dc2-e4e368d1a63e.png)

12. Now if we call "replace_chain()" again it will result in the same output as we have the most updated chain.

![image](https://user-images.githubusercontent.com/55524764/95603761-598f9c00-0a74-11eb-8c03-2f55387c3ae1.png)
