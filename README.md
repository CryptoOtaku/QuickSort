# QuickSort
QuickSort
public class QuickSort {
    public static void main(String[] args) {
        int[] numbers = {5, 2, 9, 1, 3};
        
        quickSort(numbers, 0, numbers.length - 1);
        
        System.out.println("Отсортированный массив:");
        for (int number : numbers) {
            System.out.print(number + " ");
        }
    }
    
    public static void quickSort(int[] array, int low, int high) {
        if (low < high) {
            int pivot = partition(array, low, high);
            quickSort(array, low, pivot - 1);
            quickSort(array, pivot + 1, high);
        }
    }
    
    public static int partition(int[] array, int low, int high) {
        int pivot = array[high];
        int i = low - 1;
        for (int j = low; j < high; j++) {
            if (array[j] <= pivot) {
                i++;
                swap(array, i, j);
            }
        }
        swap(array, i + 1, high);
        return i + 1;
    }
    
    public static void swap(int[] array, int i, int j) {
        int temp = array[i];
        array[i] = array[j];
        array[j] = temp;
    }
}
