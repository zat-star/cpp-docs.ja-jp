---
title: '&lt;system_error&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <system_error>
- system_error
dev_langs: C++
helpviewer_keywords: system_error header
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 68bfea40f926ed74afd6fd246b57d39b7225cdf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ltsystemerrorgt"></a>&lt;system_error&gt;
例外クラス `system_error` を定義するヘッダー `<system_error>` と、低レベルのシステム エラーを処理する関連テンプレートを含みます。  
  
## <a name="syntax"></a>構文  
  
```  
#include <system_error>  
```  
  
### <a name="objects"></a>オブジェクト  
  
|||  
|-|-|  
|[generic_category](../standard-library/system-error-functions.md#generic_category)|一般的なエラーのカテゴリを表します。|  
|[system_category](../standard-library/system-error-functions.md#system_category)|低レベル システム オーバーフローによって発生したエラーのカテゴリを表します。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[generic_errno](../standard-library/system-error-typedefs.md#generic_errno)|`<errno.h>` の Posix で定義されているすべてのエラーコードのマクロにシンボル名を提供する列挙型を表す型。|  
  
### <a name="functions"></a>関数  
  
|||  
|-|-|  
|[make_error_code](../standard-library/system-error-functions.md#make_error_code)|
          `error_code` オブジェクトを作成します。|  
|[make_error_condition](../standard-library/system-error-functions.md#make_error_condition)|
          `error_condition` オブジェクトを作成します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator==](../standard-library/system-error-operators.md#op_eq_eq)|演算子の左辺のオブジェクトが右辺のオブジェクトと等しいかどうかを調べます。|  
|[operator!=](../standard-library/system-error-operators.md#op_neq)|演算子の左側のオブジェクトが右側のオブジェクトと等しくないかどうかを調べます。|  
|[operator<](../standard-library/system-error-operators.md#op_lt)|オブジェクトが比較のために渡されるオブジェクトより小さいかどうかをテストします。|  
  
### <a name="enumerations"></a>列挙  
  
|||  
|-|-|  
|[errc](../standard-library/system-error-enums.md#errc)|`<errno.h>` の Posix で定義されているすべてのエラー コードのマクロにシンボル名を提供します。|  
  
### <a name="classes-and-structs"></a>クラスと構造体  
  
|||  
|-|-|  
|[error_category](../standard-library/error-category-class.md)|エラー コードのカテゴリを表すオブジェクトの抽象的な共通基底を表します。|  
|[error_code](../standard-library/error-code-class.md)|実装固有の低レベルなシステム エラーを表します。|  
|[error_condition](../standard-library/error-condition-class.md)|ユーザー定義のエラー コードを表します。|  
|[is_error_code_enum](../standard-library/is-error-code-enum-class.md)|[error_code クラス](../standard-library/error-code-class.md)列挙型をテストする型の述語を表します。|  
|[is_error_condition_enum](../standard-library/is-error-condition-enum-class.md)|[error_condition クラス](../standard-library/error-condition-class.md) 列挙型をテストする型の述語を表します。|  
|[system_error](../standard-library/system-error-class.md)|低レベル システム オーバーフローをレポートするためにスローされるすべての例外のための基底クラスを表します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<system_error>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)



