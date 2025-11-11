```
public class OrderService {
    public void createOrder(Map<Integer, Integer> items){
        var o = new Order();
          o.date = LocalTime.now();
          for (var item: items.entrySet()) {
            var rp = new RepoProducts();
            var p =  rp.getProduct(item.getKey());
            if(p.getStock() < item.getValue()) throw new IllegalArgumentException();
            var oi = new OrderItem();
            oi.quantity = item.getValue();
            oi.price = p.getPrice();
            o.Items.add(oi);
        }
        var ro = new RepoOrders();
        ro.Save(o);
    }
}
```

1) El código utiliza variables cortas de una letra, por lo cual no se entiende que es lo que hace a primera vista y hay que leerlo para seguir un orden.
2) En vez de utilizar var en java podríamos utilizar el tipo explícito para dar más claridad al código sobre lo que estamos instanciando 