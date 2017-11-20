---
title: "方法: 登録を必要としない COM コンポーネントをビルド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bba711f88a53a3d9b6f9eae1faed09670e95d497
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-build-registration-free-com-components"></a>方法 : 登録を必要としない COM をビルドする
登録を必要としない COM コンポーネントは、Dll に組み込まれているマニフェストのある COM コンポーネントです。  
  
### <a name="to-build-manifests-into-com-components"></a>COM コンポーネントにマニフェストをビルドするには  
  
1.  COM コンポーネントのプロジェクトのプロパティ ページを開きます。  
  
2.  展開、**構成プロパティ** ノードの順に展開し、**マニフェスト ツール**ノード。  
  
3.  選択、**の入力し、出力**プロパティ ページ、および設定、**埋め込みマニフェスト**プロパティを等しく**はい**です。  
  
4.  **[OK]** をクリックします。  
  
5.  ソリューションをビルドします。  
  
## <a name="see-also"></a>関連項目  
 [分離アプリケーション](http://msdn.microsoft.com/library/aa375190)   
 [サイド バイ サイド アセンブリの概要](http://msdn.microsoft.com/library/ff951640)   
 [方法 : COM コンポーネントを使用する分離アプリケーションをビルドする](../build/how-to-build-isolated-applications-to-consume-com-components.md)