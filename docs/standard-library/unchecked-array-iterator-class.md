---
title: "unchecked_array_iterator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "unchecked_array_iterator"
  - "stdext::unchecked_array_iterator"
dev_langs: 
  - "C++"
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# unchecked_array_iterator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`unchecked_array_iterator` クラスを使用すると、配列またはポインターをチェックを行わない反復子にラップできます。  チェックを行わないポインター警告をグローバルに抑制する代わりに、これらの警告を管理するのに適した方法として、このクラスを生のポインターまたは配列のラッパーとして使用します \([make\_unchecked\_array\_iterator](../Topic/make_unchecked_array_iterator.md) 関数を使用\)。  可能な場合は、このクラスのチェックを行うバージョンである [checked\_array\_iterator](../standard-library/checked-array-iterator-class.md) が推奨されます。  
  
> [!NOTE]
>  このクラスは、標準 C\+\+ ライブラリの Microsoft 拡張機能です。  この関数を使用して実装されるコードは、Microsoft 拡張機能をサポートしない C\+\+ 標準ビルド環境には移植できません。  
  
## 構文  
  
```  
template <class Iterator>  
    class unchecked_array_iterator;  
```  
  
## 解説  
 このクラスは、[stdext](../Topic/stdext%20Namespace.md) 名前空間で定義されます。  
  
 これは、[checked\_array\_iterator クラス](../standard-library/checked-array-iterator-class.md)のチェックを行わないバージョンであり、すべての同じオーバーロードおよびメンバーをサポートします。  チェックを行う反復子の機能とコード例の詳細については、「[チェックを行う反復子](../standard-library/checked-iterators.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:**\<iterator\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<iterator\>](../standard-library/iterator.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)