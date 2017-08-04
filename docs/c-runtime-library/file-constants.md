---
title: "ファイル定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _O_EXCL
- _O_RDWR
- _O_APPEND
- _O_RDONLY
- _O_TRUNC
- _O_CREAT
- _O_WRONLY
dev_langs:
- C++
helpviewer_keywords:
- _O_RDWR constant
- O_EXCL constant
- O_RDWR constant
- O_WRONLY constant
- O_APPEND constant
- O_CREAT constant
- _O_CREAT constant
- _O_APPEND constant
- _O_EXCL constant
- O_TRUNC constant
- _O_RDONLY constant
- _O_TRUNC constant
- O_RDONLY constant
- _O_WRONLY constant
ms.assetid: c8fa5548-9ac2-4217-801d-eb45e86f2fa4
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 354d107b9bbaf3f60153fbce5ee66b14e2a5b96d
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="file-constants"></a>ファイル定数
## <a name="syntax"></a>構文  
  
```  
  
#include <fcntl.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 以下の 1 つまたは複数の定数で形成される整数式によって、許可される読み取りまたは書き込みの操作の種類が決定されます。 これは、1 つまたは複数の定数と、変換モードの定数を組み合わせることによって形成されます。  
  
 ファイル定数は次のとおりです。  
  
 `_O_APPEND`  
 書き込み操作の前に、ファイル ポインターの位置をファイルの終端に変更します。  
  
 `_O_CREAT`  
 書き込み用の新しいファイルを作成して開きます。*filename* で指定されたファイルが存在する場合は、効果がありません。  
  
 `_O_EXCL`  
 *filename* で指定されたファイルが存在する場合は、エラー値を返します。 `_O_CREAT` と共に使用された場合にのみ適用されます。  
  
 `_O_RDONLY`  
 読み取り専用のファイルを開きます。このフラグを指定すると、`_O_RDWR` と `_O_WRONLY` は指定できません。  
  
 `_O_RDWR`  
 読み取りと書き込み両方のファイルを開きます。このフラグを指定すると、`_O_RDONLY` と `_O_WRONLY` は指定できません。  
  
 `_O_TRUNC`  
 既存のファイルを開き、長さをゼロに切り詰めます。ファイルに書き込みアクセス許可が必要です。 ファイルの内容は破棄されます。 このフラグを指定すると、`_O_RDONLY` は指定できません。  
  
 `_O_WRONLY`  
 書き込み専用のファイルを開きます。このフラグを指定すると、`_O_RDONLY` と `_O_RDWR` は指定できません。  
  
## <a name="see-also"></a>関連項目  
 [_open、_wopen](../c-runtime-library/reference/open-wopen.md)   
 [_sopen、_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)
