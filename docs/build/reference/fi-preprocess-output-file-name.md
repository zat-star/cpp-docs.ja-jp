---
title: "-Fi (出力ファイル名のプリプロセス) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Fi
dev_langs:
- C++
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9bc3076a529984358aed16902f509ceb01423f9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (出力ファイル名のプリプロセス)
出力ファイルの名前を指定、 [/P (プリプロセス出力ファイルへの)](../../build/reference/p-preprocess-to-a-file.md)コンパイラ オプションは、プリプロセス済みの出力を書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
/Fipathname  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`pathname`|によって生成される出力ファイルのパスと名前、 **/P**コンパイラ オプション。|  
  
## <a name="remarks"></a>コメント  
 使用して、 **/Fi**コンパイラ オプションと組み合わせて、 **/P**コンパイラ オプション。  
  
 パスのみを指定する場合、`pathname`プリプロセス済みの出力ファイルの基本名とパラメーター、ソース ファイルのベース名を使用します。 `pathname`パラメーターでは、特定のファイル名拡張子は必要ありません。 ただし、".i"の拡張機能は、ファイル名拡張子が指定されていない場合に使用されます。  
  
## <a name="example"></a>例  
 次のコマンド ライン PROGRAM.cpp を前処理し、コメントを保持、追加[#line](../../preprocessor/hash-line-directive-c-cpp.md)ディレクティブは、その結果を MYPROCESS.i ファイルに書き込みます。  
  
```  
CL /P /FiMYPROCESS.I PROGRAM.CPP  
```  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [/P (ファイルへのプリプロセス)](../../build/reference/p-preprocess-to-a-file.md)   
 [パス名の指定](../../build/reference/specifying-the-pathname.md)