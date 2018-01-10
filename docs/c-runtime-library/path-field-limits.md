---
title: "パス フィールドの制限 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _MAX_EXT
- _MAX_DIR
- _MAX_PATH
- _MAX_FNAME
- _MAX_DRIVE
dev_langs: C++
helpviewer_keywords:
- path field constants
- MAX_FNAME constant
- _MAX_DIR constant
- _MAX_DRIVE constant
- paths, maximum limit
- _MAX_PATH constant
- MAX_DRIVE constant
- _MAX_FNAME constant
- _MAX_EXT constant
- MAX_DIR constant
- MAX_EXT constant
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c585afee6bbea3d0cc48b696bc005b9a8d6c7992
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="path-field-limits"></a>パス フィールドの制限
## <a name="syntax"></a>構文  
  
```  
#include <stdlib.h>  
```  
  
## <a name="remarks"></a>コメント  
 これらの定数は、パスやパス内の個々のフィールドなどの最大長を定義します。  
  
|定数|説明|  
|--------------|-------------|  
|`_MAX_DIR`|ディレクトリのコンポーネントの最大長|  
|`_MAX_DRIVE`|ドライブのコンポーネントの最大長|  
|`_MAX_EXT`|拡張機能コンポーネントの最大長|  
|`_MAX_FNAME`|ファイル名のコンポーネントの最大長|  
|`_MAX_PATH`|完全なパスの最大長|  
  
> [!NOTE]
>  C ランタイムでは最大 32768 文字のパスの長さがサポートされますが、このように長いパスがサポートされるかどうかは、オペレーティング システム、特にファイル システム次第です。 FAT32 ファイル システムとの完全な下位互換性を維持するために、フィールドの合計は `_MAX_PATH` を超えないようにする必要があります。 [!INCLUDE[win2kfamily](../c-runtime-library/includes/win2kfamily_md.md)]、[!INCLUDE[WinXpFamily](../atl/reference/includes/winxpfamily_md.md)]、[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]、Windows Vista の NTFS ファイル システムでは、最大 32768 文字の長さのパスがサポートされますが、Unicode API を使用する場合に限ります。 長いパス名を使用する場合は、パスに \\\\?\ の文字のプレフィックスを付けて、C ランタイム関数の Unicode バージョンを使用します。  
  
## <a name="see-also"></a>参照  
 [グローバル定数](../c-runtime-library/global-constants.md)