---
title: "space_info 構造体 | Microsoft Docs"
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
  - "filesystem/std::tr2::sys::space_info"
dev_langs: 
  - "C++"
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
caps.latest.revision: 13
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# space_info 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ボリュームに関する情報を保持します。  
  
## 構文  
  
```  
struct space_info;  
```  
  
## メンバー  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|`unsigned long long available`|ボリューム上のデータを表すために使用できるバイト数を表します。|  
|`unsigned long long capacity`|ボリュームを表すことのできるバイト数の合計数を表します。|  
|`unsigned long long free`|ボリューム上のデータを表すために使用されないバイト数を表します。|  
  
## 必要条件  
 **ヘッダー:** filesystem  
  
 **名前空間:** std::tr2::sys  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem\>](../Topic/%3Cfilesystem%3E.md)   
 [space 関数](http://msdn.microsoft.com/ja-jp/7fce0b0e-523b-4598-b218-47245d0204ca)   
 [ファイル システムのナビゲーション \(C\+\+\)](../standard-library/file-system-navigation.md)