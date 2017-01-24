---
title: "バッカス記法 (BNF: Backus Nauer Form) の構文について | Microsoft Docs"
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
  - "Backus Nauer Form (BNF) 構文"
  - "BNF 表記"
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
caps.latest.revision: 15
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# バッカス記法 (BNF: Backus Nauer Form) の構文について
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここで使用する ATL レジストラーのスクリプトは、BNF 構文で記述されています。BNF 構文では、次の表に示す表記を使用します。  
  
|表記規則\/記号|説明|  
|--------------|--------|  
|`::=`|等しいことを表します。|  
|`&#124;`|または|  
|`X+`|1 つ以上の `X` です。|  
|`[X]`|`X` はオプションです。  オプションの区切り記号は、`[]` で表します。|  
|**太字**のテキスト|リテラル文字列です。|  
|*斜体*のテキスト|リテラル文字列を生成する方法を示します。|  
  
 上の表で示したように、レジストラー スクリプトではリテラル文字列を使用します。  これらのリテラル文字列は、スクリプトに実際に表示される文字列です。  ATL レジストラー スクリプトで使用するリテラル文字列を次の表に示します。  
  
|リテラル文字列|アクション|  
|-------------|-----------|  
|**ForceRemove**|次のキーが指定されている場合は、そのキーを完全に削除してから再作成します。|  
|**NoRemove**|登録解除中に、次に指定されているキーを削除の対象外とします。|  
|**val**|`<Key Name>` が実際の名前付きの値であることを示します。|  
|**削除**|登録中に、次に指定されたキーを削除します。|  
|**s**|次に指定された値が文字列 \(**REG\_SZ**\) であることを示します。|  
|**d**|次に指定された値が **DWORD** 型 \(**REG\_DWORD**\) であることを示します。|  
|**m**|次に指定された値が複数の文字列 \(**REG\_MULTI\_SZ**\) であることを示します。|  
|**b**|次に指定された値がバイナリ値 \(**REG\_BINARY**\) であることを示します。|  
  
## BNF 構文の例  
 ここでは、ATL レジストラー スクリプトでの表記法およびリテラル文字列の機能を理解するうえで役立つ構文の例を示します。  
  
### 構文例 1  
  
```  
<registry expression> ::= <Add Key>  
```  
  
 `registry expression` が `Add Key` と等しいことを示します。  
  
### 構文例 2  
  
```  
<registry expression> ::= <Add Key> | <Delete Key>  
```  
  
 `registry expression` が `Add Key` または `Delete Key` と等しいことを示します。  
  
### 構文例 3  
  
```  
<Key Name> ::= '<AlphaNumeric>+'  
```  
  
 `Key Name` が 1 文字以上の `AlphaNumeric` と等しいことを示します。  
  
### 構文例 4  
  
```  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
```  
  
 `Add Key` が `Key Name` と等しく、リテラル文字列 `ForceRemove`、`NoRemove`、および `val` がオプションであることを示します。  
  
### 構文例 5  
  
```  
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0  
```  
  
 `AlphaNumeric` が NULL 以外の文字と等しいことを示します。  
  
### 構文例 6  
  
```  
val 'testmulti' = m 'String 1\0String 2\0'  
```  
  
 キー名 `testmulti` は、`String 1` と `String 2` から成る複数の文字列値です。  
  
### 構文例 7  
  
```  
val 'testhex' = d '&H55'  
```  
  
 キー名 `testhex` は、16 進の 55 \(10 進の 85\) に設定された **DWORD** 値です。  この書式は、Visual Basic の仕様に見られる **&H** 表記を踏襲しています。  
  
## 参照  
 [レジストラー スクリプトの作成](../Topic/Creating%20Registrar%20Scripts.md)