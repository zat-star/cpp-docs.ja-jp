---
title: "ディレクトリ制御 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.programs
dev_langs: C++
helpviewer_keywords:
- controls [C++], directory
- directory control routines
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4674029fe5bdfc4323f580fcc0567b2ceeb1929
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="directory-control"></a>ディレクトリ制御
これらのルーチンは、ディレクトリ構造に関する情報にアクセスし、変更し、取得します。  
  
### <a name="directory-control-routines"></a>ディレクトリ制御ルーチン  
  
|ルーチンによって返される値|使用|  
|-------------|---------|  
|[_chdir、_wchdir](../c-runtime-library/reference/chdir-wchdir.md)|現在の作業ディレクトリを変更する|  
|[_chdrive](../c-runtime-library/reference/chdrive.md)|現在のドライブを変更する|  
|[_getcwd、_wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|既定のドライブの現在の作業ディレクトリを取得する|  
|[_getdcwd、_wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|指定のドライブの現在の作業ディレクトリを取得する|  
|[_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|ディスク ドライブに関する情報を `_diskfree_t` 構造体に入力する。|  
|[_getdrive](../c-runtime-library/reference/getdrive.md)|現在の (既定の) ドライブを取得する|  
|[_getdrives](../c-runtime-library/reference/getdrives.md)|現在使用できるディスク ドライブを表すビットマスクを返す。|  
|[_mkdir、_wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|新しいディレクトリを作成する|  
|[_rmdir、_wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|ディレクトリを削除します|  
|[_searchenv、_wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md)、[_searchenv_s、_wsearchenv_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|指定のパスで特定のファイルを検索する|  
  
## <a name="see-also"></a>参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)   
 [ファイル処理](../c-runtime-library/file-handling.md)   
 [システム コール](../c-runtime-library/system-calls.md)