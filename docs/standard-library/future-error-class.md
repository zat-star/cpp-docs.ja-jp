---
title: "future_error クラス | Microsoft Docs"
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
  - "future/std::future_error"
dev_langs: 
  - "C++"
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# future_error クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[今後](../standard-library/future-class.md) オブジェクトを管理する型のメソッドによってスローすることのできる例外オブジェクトを表します。  
  
## 構文  
  
```  
class future_error : public logic_error {  
public:  
   future_error(error_code code);  
   const error_code& code() const throw();  
   const char *what() const throw();  
};  
```  
  
## 必要条件  
 **ヘッダー:** future  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [logic\_error クラス](../standard-library/logic-error-class.md)   
 [error\_code クラス](../standard-library/error-code-class.md)