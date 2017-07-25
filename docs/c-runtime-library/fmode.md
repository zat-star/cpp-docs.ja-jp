---
title: "_fmode | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- fmode
- _fmode
dev_langs:
- C++
helpviewer_keywords:
- file translation [C++], default mode
- fmode function
- _fmode function
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 3c0946419e1c0a408a7dfad190387f0165d9fba0
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="fmode"></a>_fmode
`_fmode` 変数では、テキストまたはバイナリの変換のための既定のファイル変換モードを設定します。 このグローバル変数は使用されなくなりました。セキュリティを強化したバージョンである [_get_fmode](../c-runtime-library/reference/get-fmode.md) および [_set_fmode](../c-runtime-library/reference/set-fmode.md) を、グローバル変数の代わりに使用する必要があります。 これは、Stdlib.h で次のように宣言されています。  
  
## <a name="syntax"></a>構文  
  
```  
extern int _fmode;  
```  
  
## <a name="remarks"></a>コメント  
 `_fmode` の既定の設定は、テキスト モード用の `_O_TEXT` です。 `_O_BINARY` はバイナリ モード用の設定です。  
  
 `_fmode` の値は、次の 3 つの方法で変更できます。  
  
-   Binmode.obj とリンクします。 これにより、`_fmode` の初期設定が `_O_BINARY` に変更され、その結果 `stdin`、`stdout`、および `stderr` を除くすべてのファイルがバイナリ モードで開かれるようになります。  
  
-   `_get_fmode` または `_set_fmode` を呼び出して、`_fmode` グローバル変数を取得または設定します。  
  
-   `_fmode` をプログラム内に設定してその値を直接変更します。  
  
## <a name="see-also"></a>関連項目  
 [グローバル変数](../c-runtime-library/global-variables.md)   
 [_get_fmode](../c-runtime-library/reference/get-fmode.md)   
 [_set_fmode](../c-runtime-library/reference/set-fmode.md)
