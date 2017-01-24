---
title: "&lt;system_error&gt; | Microsoft Docs"
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
  - "std.<system_error>"
  - "std::<system_error>"
  - "<system_error>"
  - "system_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "system_error ヘッダー"
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;system_error&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

例外クラス `system_error` および低レベルのシステム エラーを処理するための関連テンプレートを定義するに `<system_error>` ヘッダーを含めます。  
  
## 構文  
  
```  
#include <system_error>  
```  
  
### オブジェクト  
  
|||  
|-|-|  
|[generic\_category](../Topic/generic_category.md)|一般的なエラーのカテゴリを表します。|  
|[system\_category](../Topic/system_category.md)|低レベルのシステムによるオーバーフロー エラーのカテゴリを表します。|  
  
### Typedef  
  
|||  
|-|-|  
|[generic\_errno](../Topic/generic_errno.md)|すべてのエラー コードのマクロにシンボル名を指定する列挙体を表す型は `<errno.h>`の Posix で定義されています。|  
  
### 関数  
  
|||  
|-|-|  
|[make\_error\_code](../Topic/make_error_code.md)|`error_code` オブジェクトを作成します。|  
|[make\_error\_condition](../Topic/make_error_condition.md)|`error_condition` オブジェクトを作成します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\=\=](../Topic/operator==%20\(%3Csystem_error%3E\).md)|演算子の左側のオブジェクトが右側オブジェクトと等しいかどうかをテストします。|  
|[operator\!\=](../Topic/operator!=%20\(%3Csystem_error%3E\).md)|演算子の左側のオブジェクトが右側オブジェクトと等しくないかどうかをテストします。|  
|[operator\<](../Topic/operator%3C%20\(%3Csystem_error%3E\).md)|オブジェクトである場合、比較対象に渡されるオブジェクトより小さいかどうかを調べます。|  
  
### 列挙型  
  
|||  
|-|-|  
|[errc](../Topic/errc%20Enumeration.md)|`<errno.h>` の Posix で定義されているすべてのエラー コードのマクロにシンボル名を提供します。|  
  
### Classes and Structs  
  
|||  
|-|-|  
|[error\_category](../standard-library/error-category-class.md)|abstract、エラー コードのカテゴリを記述するオブジェクトの共通ベースを表します。|  
|[error\_code](../standard-library/error-code-class.md)|実装固有である低レベルのシステム エラーを表します。|  
|[error\_condition](../standard-library/error-condition-class.md)|ユーザー定義のエラー コードを表します。|  
|[is\_error\_code\_enum](../standard-library/is-error-code-enum-class.md)|この型述語を [error\_code クラス](../standard-library/error-code-class.md) の列挙体のテスト表します。|  
|[is\_error\_condition\_enum](../standard-library/is-error-condition-enum-class.md)|この型述語を [error\_condition クラス](../standard-library/error-condition-class.md) の列挙体のテスト表します。|  
|[system\_error](../standard-library/system-error-class.md)|完全にスローされたすべての例外の基本クラスを下位システム オーバーフローを報告することを表します。|  
  
## 必要条件  
 **ヘッダー:** \<system\_error\>  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)