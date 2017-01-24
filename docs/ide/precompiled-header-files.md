---
title: "プリコンパイル済みヘッダー ファイル | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ""stdafx.h""
  - "stdafx.h"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stdafx.h"
  - "PCH ファイル、ファイルの説明"
  - ".pch ファイル、ファイルの説明"
  - "プリコンパイル済みヘッダー ファイル、ファイルの説明"
  - "stdafx.cpp"
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プリコンパイル済みヘッダー ファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのファイルは、プリコンパイル済みヘッダー ファイル *Projname*.pch とプリコンパイル済み型ファイル Stdafx.obj をビルドするために使用されます。  
  
 また、これらのファイルは *Projname* ディレクトリに配置されます。 ソリューション エクスプローラーでは、Stdafx.h が Header Files フォルダーに配置され、Stdafx.cpp が Source Files フォルダーに配置されます。  
  
|ファイル名|説明|  
|-----------|--------|  
|Stdafx.h|頻繁に使用されるものの、ほとんど変更されない標準のシステム インクルード ファイルとプロジェクト固有のインクルード ファイル用のインクルード ファイル。<br /><br /> stdafx.h で \_AFX\_NO\_XXX マクロのいずれかを定義または定義解除しないでください。サポート技術情報の記事「PRB: \_AFX\_NO\_XXX を定義するときに問題が発生する」を参照してください。 サポート技術情報の記事は、MSDN ライブラリまたは [http:\/\/ support.microsoft.com\/](http://%20support.microsoft.com/) で参照できます。|  
|Stdafx.cpp|プリプロセッサ ディレクティブ `#include "stdafx.h"` が含まれており、プリコンパイル済み型用のインクルード ファイルが追加されています。 ヘッダー ファイルなどの任意の型のプリコンパイル済みファイルは、コンパイルが必要なファイルだけにコンパイルを制限することで、コンパイル時間の短縮を支援します。 初めてプロジェクトをビルドすると、プリコンパイル済みヘッダー ファイルが存在することによって、その後のビルドは非常に速くなることに気付くでしょう。|  
  
## 参照  
 [Visual C\+\+ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)   
 [方法 : \[プロパティ ページ\] でプロジェクトのプロパティを指定する](../Topic/How%20to:%20Specify%20Project%20Properties%20with%20Property%20Pages.md)