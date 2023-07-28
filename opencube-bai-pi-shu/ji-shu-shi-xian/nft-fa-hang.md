# NFT发行

在合约中定义一个函数，`mintNFT`，用于创建新的NFT。该函数接受参数，包括NFT名称、描述、图像链接等，并为新创建NFT分配一个唯一的标识。在函数内部，使用ERC1155合约供的`_mint`函数来创建新的NFT，并将其分配给指定的地址。
