---
title: "サンプル コンテナーのメンバー | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コンテナー クラス"
ms.assetid: dc5a1998-a31b-4adf-b888-8abe5b87a4e0
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# サンプル コンテナーのメンバー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  このトピックでは、標準 C\+\+ ライブラリで使用されるコンテナーの、機能的な例として、Visual C\+\+ のドキュメントにあります。  詳細については、「[STL コンテナー](../standard-library/stl-containers.md)」を参照してください。  
  
## 関連項目  
  
## Typedef  
  
|||  
|-|-|  
|[const\_iterator](../standard-library/container-class-const-iterator.md)|被制御シーケンスの定数反復子として使用できるオブジェクトを表します。|  
|[const\_reference](../standard-library/container-class-const-reference.md)|被制御シーケンスの要素への定数参照として使用できるオブジェクトを表します。|  
|[const\_reverse\_iterator](../standard-library/container-class-const-reverse-iterator.md)|被制御シーケンスの定数反転反復子として使用できるオブジェクトを表します。|  
|[difference\_type](../Topic/Container%20Class::difference_type.md)|被制御シーケンスの任意の 2 要素のアドレスの違いを表現できるオブジェクトを表します。|  
|[iterator](../standard-library/container-class-iterator.md)|被制御シーケンスの反復子として使用できるオブジェクトを表します。|  
|[参照](../Topic/Container%20Class::reference.md)|被制御シーケンスの要素への参照として使用できるオブジェクトを表します。|  
|[reverse\_iterator](../standard-library/container-class-reverse-iterator.md)|被制御シーケンスの反転反復子として使用できるオブジェクトを表します。|  
|[size\_type](../standard-library/container-class-size-type.md)|すべての被制御シーケンスの長さを表現できるオブジェクトを表します。|  
|[value\_type](../standard-library/container-class-value-type.md)|テンプレート パラメーター **Ty**のシノニムを満たします。|  
  
## メンバー関数  
  
|||  
|-|-|  
|[begin](../standard-library/container-class-begin.md)|シーケンスの最初の要素を指す反復子を返します \(または空のシーケンスの末尾の次の位置\)。|  
|[clear](../standard-library/container-class-clear.md)|[erase](../standard-library/container-class-erase.md) \([開始](../standard-library/container-class-begin.md)、[終了](../Topic/Container%20Class::end.md)\) を呼び出します。|  
|[empty](../standard-library/container-class-empty.md)|空の被制御シーケンスの **true** を返します。|  
|[End](../Topic/Container%20Class::end.md)|シーケンスの末尾の次の位置を指し示す前方反復子を返します。|  
|[erase](../standard-library/container-class-erase.md)|要素を消去します。|  
|[max\_size](../standard-library/container-class-max-size.md)|被制御シーケンスの長さに関係なく、オブジェクトが制御できる定数時間で最も長いシーケンスの長さを返します。|  
|[rbegin](../Topic/Container%20Class::rbegin.md)|被制御シーケンスの末尾の次の位置を指し示す反転シーケンスの先頭を指定する反転反復子を返します。|  
|[rend](../standard-library/container-class-rend.md)|このメンバー関数は、シーケンスの最初の要素を指す反転シーケンスの末尾を指定する反転反復子 \(または空のシーケンスの末尾の次の位置\) を返します。|  
|[size](../standard-library/container-class-size.md)|被制御シーケンスの長さに関係なく定数時間の被制御シーケンスの長さを返します。|  
|[swap](../Topic/Container%20Class::swap.md)|**\*this** と `_Right`間で被制御シーケンスを交換します。|