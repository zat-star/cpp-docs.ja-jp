---
title: "region、endregion | Microsoft Docs"
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
  - "vc-pragma.endregion"
  - "endregion_CPP"
  - "region_CPP"
  - "vc-pragma.region"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "endregion プラグマ"
  - "プラグマ, endregion"
  - "プラグマ, 領域"
  - "region プラグマ"
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# region、endregion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\#pragma region** を使用してコードのブロックを指定します。このブロックは、Visual Studio コード エディターの[アウトライン](../Topic/Outlining.md)機能を使用して展開や折りたたみができます。  
  
## 構文  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
#### パラメーター  
 `comment` \(省略可能\)  
 コード エディターに表示されるコメント。  
  
 *name* \(省略可能\)  
 領域の名前。  この名前はコード エディターに表示されます。  
  
## 解説  
 **\#pragma endregion** は **\#pragma region** ブロックの末尾を示します。  
  
 `#region` ブロックは **\#pragma endregion** で終了させる必要があります。  
  
## 使用例  
  
```  
// pragma_directives_region.cpp  
#pragma region Region_1  
void Test() {}  
void Test2() {}  
void Test3() {}  
#pragma endregion Region_1  
  
int main() {}  
```  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)