---
title: ATL レジストラーおよびバッカスナウア Nauer フォーム (BNF) 構文 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BNF notation
- Backus Nauer Form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4137dd94886456d5813076f3cb328bac5ecf5c03
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="understanding-backus-nauer-form-bnf-syntax"></a>バッカスナウア Nauer Form (BNF) の構文の理解
ATL レジストラーで使用されるスクリプトは、次の表に示すように表記を使用して BNF 構文を使用して、このトピックで説明します。  
  
|規則および記号|説明|  
|------------------------|-------------|  
|`::=`|同等の表記|  
|`&#124;`|OR|  
|`X+`|1 つまたは複数`X`s。|  
|`[X]`|`X` は省略可能です。 省略可能な区切り記号で示されます`[]`です。|  
|どの**太字**テキスト|文字列リテラルです。|  
|どの*斜体*テキスト|文字列リテラルを作成する方法です。|  
  
 示されるように前の表に、レジストラー スクリプトは、文字列リテラルを使用します。 これらの値は、実際のテキストをスクリプト内で使用する必要があります。 次の表では、ATL レジストラー スクリプトで使用されるリテラル文字列について説明します。  
  
|文字列リテラル|アクション|  
|--------------------|------------|  
|**ForceRemove**|(存在する場合は、次のキーを完全に削除してから再作成します。|  
|**NoRemove**|登録解除中に次のキーは削除されません。|  
|**val**|指定する`<Key Name>`が実際には名前付きの値。|  
|**削除**|登録中に次のキーを削除します。|  
|**s**|次の値を文字列に指定します (**REG_SZ**)。|  
|**d**|次の値を指定します、 **DWORD** (**REG_DWORD**)。|  
|**m**|次の値を複数文字列に指定します (**REG_MULTI_SZ**)。|  
|**b**|次の値が、バイナリ値を指定します (**REG_BINARY**)。|  
  
## <a name="bnf-syntax-examples"></a>BNF 構文例  
 ATL レジストラー スクリプトで表記と文字列リテラルのしくみを理解するための構文例をいくつかのとおりです。  
  
### <a name="syntax-example-1"></a>構文例 1  
  
```  
<registry expression> ::= <Add Key>  
```  
  
 指定する`registry expression`は等価`Add Key`です。  
  
### <a name="syntax-example-2"></a>構文例 2  
  
```  
<registry expression> ::= <Add Key> | <Delete Key>  
```  
  
 指定する`registry expression`はいずれかに相当`Add Key`または`Delete Key`です。  
  
### <a name="syntax-example-3"></a>構文例 3  
  
```  
<Key Name> ::= '<AlphaNumeric>+'  
```  
  
 指定する`Key Name`は 1 つ以上に相当`AlphaNumerics`です。  
  
### <a name="syntax-example-4"></a>構文例 4  
  
```  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
```  
  
 指定`Add Key`と等価`Key Name`、および文字列リテラル`ForceRemove`、 `NoRemove`、および`val`は省略可能です。  
  
### <a name="syntax-example-5"></a>構文例 5  
  
```  
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0  
```  
  
 指定する`AlphaNumeric`を NULL 以外の文字と同じです。  
  
### <a name="syntax-example-6"></a>構文例 6  
  
```  
val 'testmulti' = m 'String 1\0String 2\0'  
```  
  
 指定したキー名`testmulti`は複数文字列値で構成されます`String 1`と`String 2`です。  
  
### <a name="syntax-example-7"></a>構文例 7  
  
```  
val 'testhex' = d '&H55'  
```  
  
 指定したキー名`testhex`は、 **DWORD**値は 16 進 55 (10 進 85) に設定します。 注この形式に従って、 **& H**として表記、Visual Basic の仕様に記載します。  
  
## <a name="see-also"></a>関連項目  
 [レジストラー スクリプトの作成](../atl/creating-registrar-scripts.md)

