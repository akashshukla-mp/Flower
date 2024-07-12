
import org.springframework.cache.annotation.Cacheable;
import org.springframework.cache.annotation.CachePut;
import org.springframework.stereotype.Service;

import java.util.HashMap;
import java.util.List;
import java.util.Map;

@Service
public class YourService {

    // Cache a map of id to object
    @Cacheable(cacheNames = "objectMapCache", key = "'objectMap'")
    public Map<String, YourObject> getCachedObjectMap() {
        return new HashMap<>(); // Initialize empty map
    }

    @CachePut(cacheNames = "objectMapCache", key = "'objectMap'")
    public Map<String, YourObject> updateObjectMap(String id, YourObject obj) {
        Map<String, YourObject> map = getCachedObjectMap();
        map.put(id, obj);
        return map;
    }

    // Cache a map of id to list of objects
    @Cacheable(cacheNames = "listMapCache", key = "'listMap'")
    public Map<String, List<YourObject>> getCachedListMap() {
        return new HashMap<>(); // Initialize empty map
    }

    @CachePut(cacheNames = "listMapCache", key = "'listMap'")
    public Map<String, List<YourObject>> updateListMap(String id, List<YourObject> objList) {
        Map<String, List<YourObject>> map = getCachedListMap();
        map.put(id, objList);
        return map;
    }

    // Function to get all ids from object map
    public List<String> getObjectIds() {
        return List.copyOf(getCachedObjectMap().keySet());
    }

    // Function to get all ids from list map
    public List<String> getListIds() {
        return List.copyOf(getCachedListMap().keySet());
    }
}


<h1>E-commerce Flower Shop</h1>
<p>Welcome to our enchanting online flower emporium! 🌸 This project is a seamless blend of nature's beauty and cutting-edge web technologies. Dive into the world of vibrant blooms, elegantly showcased through an Owl Carousel, complemented by captivating animations using the Aios library. The site, built with HTML, CSS, JavaScript, Bootstrap, and jQuery, offers a responsive design for a delightful user experience on any device. Connect with us effortlessly through social media icons and a user-friendly contact form. Explore the repository and witness the bloom of nature in the digital realm.</p>

<h3>Technologies Used:</h3>
<ul>
<li>HTML</li>
<li>CSS</li>
<li>JavaScript</li>
<li>Bootstrap</li>
<li>jQuery</li>
</ul>
<h3>Features:</h3>
<ul>
<li>Owl Carousel</li>
<li>Aios Library Animations</li>
<li>Responsive Design</li>
<li>Social Media Integration</li>
<li>User-Friendly Contact Form</li>
</ul>
<br>
