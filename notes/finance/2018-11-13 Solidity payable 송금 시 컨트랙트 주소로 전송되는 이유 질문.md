# Solidity payable 송금 시 컨트랙트 주소로 전송되는 이유 질문
*작성 2018-11-13 · 수정 2018-11-13*

상황  
(Ganache)  

(In .sol file)  
function sending( address _addr) payable {  
…  
	value = msg.value;  
	_addr.transfer(value);  
...  
}  

(in web3)  
sc.sending(“0x123…”, {value : web3.toWei(3, “ether”), from:”0x234…”} );  

질문 : ”0x234…” 에서 “0x123…”로 ETH가 전송되지 않고 CA Address로 전송되는 이유?
