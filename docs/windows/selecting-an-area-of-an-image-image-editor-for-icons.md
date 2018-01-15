---
title: "イメージ (アイコン用イメージ エディター) の領域の選択 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.image.editing
dev_langs: C++
helpviewer_keywords:
- Image editor [C++], image selection
- Image editor [C++], selecting images
- images [C++], selecting
- cursors [C++], selecting areas of
ms.assetid: 8b6ce4ad-eba1-4ece-86ba-cea92c3edff2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3060c47af46a39358ac2e8a7ab5b573f50867869
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="selecting-an-area-of-an-image-image-editor-for-icons"></a>イメージの領域の選択 (アイコン用イメージ エディター)
選択ツールを使用すると、切り取り、コピー、クリア、サイズ変更、反転、または移動するイメージの領域を定義します。 **矩形選択**ツールを定義し、イメージの四角形の領域を選択できます。 **不規則選択**ツール、切り取り、コピー、またはその他の操作を選択する領域のフリーハンド アウトラインを描画することができます。  
  
> [!NOTE]
>  参照してください、**矩形選択**と**不規則選択**ツールには描か[イメージ エディター ツールバー](../windows/toolbar-image-editor-for-icons.md) の各ボタンに関連付けられているツールヒントを表示または**イメージ エディター**ツールバー。  
  
 選択範囲からカスタム ブラシを作成することもできます。 詳細については、次を参照してください。[カスタム ブラシの作成](../windows/creating-a-custom-brush-image-editor-for-icons.md)です。  
  
### <a name="to-select-an-area-of-an-image"></a>イメージの領域を選択するには  
  
1.  **イメージ エディター**ツールバー (または、**イメージ**] メニューの [**ツール**コマンド)、必要なツールを選択します。  
  
2.  選択する画像領域の 1 つ上隅にカーソルを移動します。 十字線は、挿入ポイントがイメージ上に表示されます。  
  
3.  選択する領域の反対側の隅にカーソルをドラッグします。 四角形に表示されるピクセルが選択されます。 選択範囲には、四角形の下にあるものを含む四角形内のすべてのピクセルが含まれています。  
  
4.  マウスのボタンを離します。 選択範囲の境界線では、選択した領域を囲みます。  
  
### <a name="to-select-an-entire-image"></a>イメージ全体を選択するには  
  
1.  現在の選択範囲の外部でイメージをクリックします。 選択範囲の境界線はフォーカスを変更し、もう一度画像全体が含まれます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 必要条件  
  
 なし  
  
## <a name="see-also"></a>参照  
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   
 [グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)

