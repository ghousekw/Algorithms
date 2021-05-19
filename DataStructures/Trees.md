# Trees

* Tree jo hy woh **`hierarchical data structrure.`** 
* Start hota parent element se phir sub element aur uske sub elements.
* Important terms in trees are
    - Node
        - jabbi har element convert hota form me
    - Root
        - Starting point bolsakte ho
    - Parent
    - Child
    - Leaf node
        - last element that has no child 
    - Sibling
    - Edge
        - connection of one element to another element
    - Levels
        - levels like parent, child ...
    - Path
        - path kato ek node se dusre node ka path
        - jaise 3-9 path bole tho 3-2-5-9 aisa
    - Subtrees
        - bole tho tree me ek child aur uske children ko alag se nikal le tho woh hisse ko sub trees boltin


![trees](../images/Trees.png)

* Chalo ek real life scenario lekar dekhte hyn.

![trees](../images/TreesInRealScenario.png)

* Yahan par mera status jo hy woh root node hoga aur comments jo hy woh child nodes, aur replies uske child nodes waisa.

* Hum html file bi example ke tarah dekh sakte hyn, jaise usme root tag html hota hy aur head, body uske child tags ke jaisa, aur body me phir sub tags rehtin waisa.

* Child ko sirf ek hi parent rahega.
* Direction me dekhe tho hum left yaan child me jasakte hyn.

* Trees me 2 important terms jaise

![trees](../images/TreesDepthHeight.png)

### Depth
        - Depth boleto kaunse bi node se shuru hoke root node tak, kitne edges lagi woh dekhte hyn.
        - The depth of any node is the number of edges from that node to the root node.

### Height:

        - Height boleto kaunse bi node se shuru hoke use sab se akhir wale node tak kitne edges hy woh boltin.
        - The height of any node is the number of edges from that node to that deapest leaf.

![trees](../images/TreesHeightRep.png)

* Agar my yeh tree ka height bolun tho, 3 hy, jaise     A->D->G->H.
    - Height of tree = Height of root node.
* Aur Node H depth bolun tho 3 hy, jaise H->G->D->A

![trees](../images/TreesExample.png)

* Agar edges calculate kare tho
    - Number of nodes - 1(root node)