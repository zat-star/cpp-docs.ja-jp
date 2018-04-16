---
title: VCPROFILE_PATH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VCPROFILE_PATH
dev_langs:
- C++
helpviewer_keywords:
- VCPROFILE_PATH environment variable
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea682b70f4417ef49bfca530af5f12f21699a389
ms.sourcegitcommit: 5cd2e3e51ecc8d9fc0d889555b4bfa193ba1d6a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2018
---
# <a name="vcprofilepath"></a>VCPROFILE_PATH
.Pgc ファイルを作成するディレクトリを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
VCPROFILE_PATH=path  
```  
  
#### <a name="parameters"></a>パラメーター  
 `path`  
 .Pgc ファイルを追加するディレクトリ パス。  
  
## <a name="remarks"></a>コメント  
 既定では、.pgc ファイルは、プロファイリング対象のバイナリと同じディレクトリに作成されます。  ただし、バイナリの絶対パスが存在しない場合、バイナリが構成されているとは異なるマシンでプロファイルのシナリオを実行すると、大文字と小文字をすることがある、設定できます`VCPROFILE_PATH`が存在するパスにします。  
  
## <a name="example"></a>例  
  
```  
set VCPROFILE_PATH=c:\  
```  
  
## <a name="see-also"></a>関連項目  
 [ガイド付き最適化のプロファイルの環境変数](../../build/reference/environment-variables-for-profile-guided-optimizations.md)