---
title: "プリコンパイル済みヘッダー ファイルの |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdafx.h
dev_langs:
- C++
helpviewer_keywords:
- stdafx.h
- PCH files, file descriptions
- .pch files, file descriptions
- precompiled header files, file descriptions
- stdafx.cpp
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1208b000f57397764277cc0a43e223f7c781a06e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="precompiled-header-files"></a>プリコンパイル済みヘッダー ファイル
これらのファイルは、プリコンパイル済みヘッダー ファイル *Projname*.pch とプリコンパイル済み型ファイル Stdafx.obj をビルドするために使用されます。  
  
 また、これらのファイルは *Projname* ディレクトリに配置されます。 ソリューション エクスプローラーでは、Stdafx.h が Header Files フォルダーに配置され、Stdafx.cpp が Source Files フォルダーに配置されます。  
  
|ファイル名|説明|  
|---------------|-----------------|  
|stdafx.h|頻繁に使用されるものの、ほとんど変更されない標準のシステム インクルード ファイルとプロジェクト固有のインクルード ファイル用のインクルード ファイル。<br /><br /> stdafx.h で _AFX_NO_XXX マクロのいずれかを定義または定義解除しないでください。サポート技術情報の記事「PRB: _AFX_NO_XXX を定義するときに問題が発生する」を参照してください。 サポート技術情報の記事は、MSDN ライブラリまたは [http:// support.microsoft.com/](http://%20support.microsoft.com/)で参照できます。|  
|stdafx.cpp|プリプロセッサ ディレクティブ `#include "stdafx.h"` が含まれており、プリコンパイル済み型用のインクルード ファイルが追加されています。 ヘッダー ファイルなどの任意の型のプリコンパイル済みファイルは、コンパイルが必要なファイルだけにコンパイルを制限することで、コンパイル時間の短縮を支援します。 初めてプロジェクトをビルドすると、プリコンパイル済みヘッダー ファイルが存在することによって、その後のビルドは非常に速くなることに気付くでしょう。|  
  
## <a name="see-also"></a>参照  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)   
 [プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)