---
title: "方法: COM コンポーネントを使用する分離アプリケーションをビルド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aaeef56f122d10f983313ab1c839db40f4e92aa4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>方法 : COM コンポーネントを使用する分離アプリケーションをビルドする
分離アプリケーションは、プログラムに組み込まれたマニフェストがあるアプリケーションです。 COM コンポーネントを使用する分離アプリケーションを作成することができます。  
  
### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>分離アプリケーションのマニフェストを COM 参照を追加するには  
  
1.  分離アプリケーションのプロジェクトのプロパティ ページを開きます。  
  
2.  展開、**構成プロパティ** ノードの順に展開し、**マニフェスト ツール**ノード。  
  
3.  選択、**分離された COM**プロパティ ページ、および設定、**コンポーネントのファイル名**プロパティを使用する分離アプリケーションで、使用する COM コンポーネントの名前にします。  
  
4.  **[OK]**をクリックします。  
  
### <a name="to-build-manifests-into-isolated-applications"></a>分離アプリケーション マニフェストをビルドするには  
  
1.  分離アプリケーションのプロジェクトのプロパティ ページを開きます。  
  
2.  展開、**構成プロパティ** ノードの順に展開し、**マニフェスト ツール**ノード。  
  
3.  選択、**の入力し、出力**プロパティ ページ、および設定、**埋め込みマニフェスト**プロパティを等しく**はい**です。  
  
4.  **[OK]**をクリックします。  
  
5.  ソリューションをビルドします。  
  
## <a name="see-also"></a>参照  
 [分離アプリケーション](http://msdn.microsoft.com/library/aa375190)   
 [サイド バイ サイド アセンブリの概要](http://msdn.microsoft.com/library/ff951640)