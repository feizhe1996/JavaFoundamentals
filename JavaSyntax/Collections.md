# Collections: Set, List, Map

![collections](collections.png)



## iterator

```{java}
public static void main(String[] args)
{
    Set<String> set = new HashSet<String>();
    set.add("Rain");
    set.add("In");
    set.add("Spain");

     // Get an iterator for the set
     Iterator<String> iterator = set.iterator();

    while (iterator.hasNext())        // Check if there is another element
    {
       // Get the current element and move to the next one
       String text = iterator.next();

        System.out.println(text);
    }
}
```



## display elements of a map

```{java}
public static void main(String[] args)
{
    // All elements are stored in pairs
    Map<String, String> map = new HashMap<String, String>();
    map.put("first", "Rain");
    map.put("second", "In");
    map.put("third", "Spain");

    Iterator<Map.Entry<String, String>> iterator = map.entrySet().iterator();

   while (iterator.hasNext())
    {
        // Get a key-value pair
        Map.Entry<String, String> pair = iterator.next();
        String key = pair.getKey();            // Key
        String value = pair.getValue();        // Value
        System.out.println(key + ":" + value);
    }
}
```

or

```{java}
public static void main(String[] args)
{
    Map<String, String> map = new HashMap<String, String>();
    map.put("first", "Rain");
    map.put("second", "In");
    map.put("third", "Spain");

    for (Map.Entry<String, String> pair : map.entrySet())
    {
        String key = pair.getKey();                      // Key
        String value = pair.getValue();                  // Value
        System.out.println(key + ":" + value);
    }
}
```

