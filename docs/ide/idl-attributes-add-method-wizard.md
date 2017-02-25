---
title: "[IDL 属性] (メソッド追加ウィザード) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.method.idlattrib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メソッド追加ウィザード [C++]"
  - "IDL 属性、メソッド追加ウィザード"
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# [IDL 属性] (メソッド追加ウィザード)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メソッド追加ウィザードのこのページを使用して、メソッドのインターフェイス定義言語 \(IDL: Interface Definition Language\) の設定を行います。  
  
 **id**  
 メソッドを識別する数字の ID を設定します。  「MIDL Language Reference」の「[id](http://msdn.microsoft.com/library/windows/desktop/aa367040)」を参照してください。  
  
 このボックスは、カスタム インターフェイスでは無効です。MFC ディスパッチ インターフェイスでは使用できません。  
  
 **call\_as**  
 このローカル メソッドを割り当てることができるリモート メソッドの名前を指定します。  「MIDL Language Reference」の「[call\_as](http://msdn.microsoft.com/library/windows/desktop/aa366748)」を参照してください。  
  
 MFC ディスパッチ インターフェイスでは使用できません。  
  
 **helpcontext**  
 この要素に関するヘルプ ファイルの情報をユーザーが表示できるようにするためのコンテキスト ID を指定します。  「MIDL Language Reference」の「[helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851)」を参照してください。  
  
 MFC ディスパッチ インターフェイスでは使用できません。  
  
 **helpstring**  
 適用先の要素の記述に使用される文字列を指定します。  既定では、"メソッド \<メソッド名\>" に設定されています。「MIDL Language Reference」の「[helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856)」を参照してください。  
  
 MFC ディスパッチ インターフェイスでは使用できません。  
  
 **Additional attributes**  
 MFC ディスパッチ インターフェイスでは使用できません。  
  
|属性|Description|  
|--------|-----------------|  
|**hidden**|項目が存在しても、ユーザー指向ブラウザーに表示されないことを示します。  「MIDL Language Reference」の「[hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861)」を参照してください。|  
|**source**|メソッドのメンバーがイベントのソースであることを示します。  「MIDL Language Reference」の「[source](http://msdn.microsoft.com/library/windows/desktop/aa367166)」を参照してください。|  
|`local`|メソッドがリモートでないことを MIDL コンパイラに指定します。  「MIDL Language Reference」の「[local](http://msdn.microsoft.com/library/windows/desktop/aa367071)」を参照してください。|  
|**restricted**|メソッドを任意に呼び出すことができないことを示します。  「MIDL Language Reference」の「[restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157)」を参照してください。|  
|**vararg**|メソッドがとる引数の数が可変であることを示します。  このためには、最後の引数が、残りすべての引数を格納する **VARIANT** 型のセーフ配列である必要があります。  「MIDL Language Reference」の「[vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304)」を参照してください。|  
  
## 参照  
 [メソッドの追加](../ide/adding-a-method-visual-cpp.md)   
 [メソッド追加ウィザード](../ide/add-method-wizard.md)