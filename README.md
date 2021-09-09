# assignment2-vobilishetty
# Praneeth Kumar Vobilishetty
###### My favorite place is New York

It was my dream to visit there, tourism in New York City is at its peak. Many visitors come there for the sake of witnessing the beautiful scenes and sights.<br> The places  include the Empire State Building, Ellis Island, **Times Square**, Statue of Liberty, **Niagara falls**.

---
# Directions from Maryville to New York
1. Book a flight ticket to New York from Kansas City
2. Start your jounrney to Kansas City from Maryville atleast three  hour before to your flight depature time and go through security checks before you board the plane.
    1. Take some food with you because you need to travel in 2 flights, there may be chance of more layover time.
    2. After reaching NewYork airport take a rental car in airport itself as public transportation is very costly in new york.
    3. Visit all important/beautiful places in new york.
3. After visiting all places return the rental car in airport and board the return flight for kansas city.


Items to be bring for your favorite place
* DSLR camera
* Light Jacket
* Comfortable Shoe
    * pair of socks
    * pair of shoe lace
* Hat
* Sunglasses

[Click on this link to know more about me](AboutMe.md)

----
## Food/Drinks I would recommend for someone

Below are the drinks I would recommend to any one for good health.

| Food/Drinks | Location | Price |
| :---: | :---: | :---: |
| Veg Biryani | Pardise | $15 |
| Cocacola | Walmart | $5 |
| Kaju Barfi| Karachi Bakery | $2 |
| Tender Coconut Icecream| Naturals | $5 |

---
## Pithy Quotes
> Tough times never last but tough people do - *Robert H. Schuller*

> You miss 100 percent of the shots you never take. - *Wayne Gretzky*

---
## Code Fencing : kruskal's algorithm

> An algorithm for computing a minimum spanning tree. It maintains a set of partial minimum spanning trees, and repeatedly adds the shortest edge in the graph whose vertices are in different partial minimum spanning trees.

<https://xlinux.nist.gov/dads/HTML/kruskalsalgo.html>

```
struct Edge {
    int u, v, weight;
    bool operator<(Edge const& other) {
        return weight < other.weight;
    }
};

int n;
vector<Edge> edges;

int cost = 0;
vector<int> tree_id(n);
vector<Edge> result;
for (int i = 0; i < n; i++)
    tree_id[i] = i;

sort(edges.begin(), edges.end());

for (Edge e : edges) {
    if (tree_id[e.u] != tree_id[e.v]) {
        cost += e.weight;
        result.push_back(e);

        int old_id = tree_id[e.u], new_id = tree_id[e.v];
        for (int i = 0; i < n; i++) {
            if (tree_id[i] == old_id)
                tree_id[i] = new_id;
        }
    }
}

```