---
title: "ウィンドウ ペイン (アイコン用イメージ エディター) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs: C++
helpviewer_keywords:
- graphics editor [C++]
- Image editor [C++], panes
ms.assetid: d66ea5b3-e2e2-4fc4-aa99-f50022cc690e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c4b28d49d698f5bc39d8a3915c635c28ecca4193
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="window-panes-image-editor-for-icons"></a>ウィンドウ ペイン (アイコン用イメージ エディター)
通常、イメージ エディター ウィンドウでは、分割バーで区切られた 2 つのペインで、イメージが表示されます。 1 つのビューは、実際のサイズと拡大、他の (既定の倍率は 6)。 これら 2 つのペインでビューが自動的に更新されます。 1 つのペインで行った変更はすぐに、他の表示。 2 つのペインを使用すると、拡大を個々 のピクセルを区別して、同時に、作業内容のイメージの実際のサイズのビューへの影響を観察、イメージの表示で動作するための簡単。  
  
 左側のウィンドウは、領域のイメージの 1:1 のビュー (既定値) を表示する (最大の半分イメージ ウィンドウ) が必要に応じて使用します。 右側のペインには、拡大イメージ (既定では 6:1 の) が表示されます。 ことができます[表示倍率の変更](../windows/changing-the-magnification-factor-image-editor-for-icons.md)各ペインを使用して、 **Magnify**ツールを[イメージ エディター ツールバー](../windows/toolbar-image-editor-for-icons.md)またはアクセラレータ キーを使用します。  
  
 イメージ エディター ウィンドウの小さいウィンドウを拡大し、サイズの大きいイメージのさまざまな地域を表示する 2 つのペインを使用できます。 選択ウィンドウをクリックします。  
  
 分割バーにポインターを移動し、右または左に分割バーを移動して、ペインの相対サイズを変更できます。 分割バーは、1 つのペインで作業する場合、どちらの側に移動できます。  
  
 場合は、イメージ エディター ウィンドウの拡大が 4 以上の要素、[ピクセル グリッドを表示](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md)イメージ内の個々 のピクセルを取り出すためです。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>必要条件  
 なし  
  
## <a name="see-also"></a>参照  
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)

