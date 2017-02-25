---
title: "パース ツリーについて | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "パース ツリー"
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# パース ツリーについて
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

各パース ツリーに次の形式を持つ、レジストラー スクリプトの一つ以上のパース ツリーを定義する:  
  
```  
<root key>{<registry expression>}+  
```  
  
 それぞれの文字について以下に説明します。  
  
```  
<root key> ::=  HKEY_CLASSES_ROOT | HKEY_CURRENT_USER |  
               HKEY_LOCAL_MACHINE | HKEY_USERS |  
               HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA |  
               HKEY_CURRENT_CONFIG | HKCR | HKCU |  
               HKLM | HKU | HKPD | HKDD | HKCC  
<registry expression> ::= <Add Key> | <Delete Key>  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
              [<Key Value>][{< Add Key>}]  
<Delete Key> ::=  Delete<Key Name>  
<Key Name> ::= '<AlphaNumeric>+'  
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0  
<Key Value> ::== <Key Type><Key Name>  
<Key Type> ::= s | d  
<Key Value> ::= '<AlphaNumeric>'  
```  
  
> [!NOTE]
>  `HKEY_CLASSES_ROOT` とは等価です `HKCR` ; `HKEY_CURRENT_USER` とは等価です `HKCU` ; します。  
  
 パース ツリーは root keyに複数のキーとサブキーを追加できます。  その際に、パーサーはサブキーをすべて分析を完了するまでサブキーのハンドルを保持しますが開きます。  この方法では、次の例に示すように、一つのキーで一度に処理するよりも効果:  
  
```  
HKEY_CLASSES_ROOT  
{  
   'MyVeryOwnKey'  
   {  
      'HasASubKey'  
      {  
         'PrettyCool?'  
      }  
   }  
}  
```  
  
 ここでは、レジストラーは、最初に `HKEY_CLASSES_ROOT\MyVeryOwnKey`を開きます \(作成します\)。  `MyVeryOwnKey` にサブキーがあることを調べます。  `MyVeryOwnKey`にキーを終了する代わりに、レジストラーは、この親ハンドルを使用してハンドルを開きます \(作成します\) `HasASubKey` 保持します。  \(システム レジストリは親のハンドルが開いていない場合よりも遅くなる可能性があります\)。したがって、親として `MyVeryOwnKey` の `HKEY_CLASSES_ROOT\MyVeryOwnKey`、を開始 `HasASubKey` 開くと、開始 `MyVeryOwnKey`、最後の `MyVeryOwnKey`を開始 `MyVeryOwnKey\HasASubKey`高速です。  
  
## 参照  
 [レジストラー スクリプトの作成](../Topic/Creating%20Registrar%20Scripts.md)