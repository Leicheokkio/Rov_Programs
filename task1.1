import cv2
import numpy as np

class PipeMeasurer:
    def __init__(self):
        self.points = []  # To store selected points
        self.original_image = None
        self.reference_length = 0  # Reference length (cm)
        self.reference_pixels = 0  # Reference length in pixels

    def mouse_callback(self, event, x, y, flags, param):
        if event == cv2.EVENT_LBUTTONDOWN:
            self.points.append((x, y))
            cv2.circle(self.original_image, (x, y), 5, (0, 0, 255), -1)
            cv2.imshow('Original Image', self.original_image)

            # If four points are selected, calculate length
            if len(self.points) == 4:
                self.calculate_unknown_length()

    def calculate_unknown_length(self):
        if len(self.points) != 4:
            return

        # Calculate pixel distances
        pixel_length_known = np.sqrt((self.points[1][0] - self.points[0][0]) ** 2 +
                                      (self.points[1][1] - self.points[0][1]) ** 2)

        pixel_length_unknown = np.sqrt((self.points[3][0] - self.points[2][0]) ** 2 +
                                        (self.points[3][1] - self.points[2][1]) ** 2)

        # Calculate the real length of the unknown object
        if self.reference_length > 0 and self.reference_pixels > 0:
            unknown_length = (pixel_length_unknown * self.reference_length) / pixel_length_known
            print(f"未知水管的實際長度: {unknown_length:.1f} cm")
        else:
            print("請先設置參考長度（按 'r' 鍵）")

    def process_image(self, image_path):
        # Read and resize image
        self.original_image = cv2.imread(image_path)
        if self.original_image is None:
            print(f"無法讀取圖片: {image_path}")
            return False

        # Resize image to half
        self.original_image = cv2.resize(self.original_image,
                                          (self.original_image.shape[1] // 2,
                                           self.original_image.shape[0] // 2))

        # Display the image
        cv2.imshow('Original Image', self.original_image)
        cv2.setMouseCallback('Original Image', self.mouse_callback)

        return True

    def set_reference(self, pixel_length, real_length):
        """Set reference length"""
        self.reference_length = real_length
        self.reference_pixels = pixel_length
        print(f"已設置參考長度: {real_length:.1f} 公分 = {pixel_length:.1f} 像素")


def main():
    # Specify the local path to the image you want to process
    image_path = "Rov photo/t1.png"  # Change this to your actual image path

    # Create an instance of the PipeMeasurer
    measurer = PipeMeasurer()

    # Process the specified image
    if measurer.process_image(image_path):
        print("請在圖片上點選四個點來測量水管長度")
        print("前兩個點為已知長度，後兩個點為未知長度")
        print("按 'r' 設置參考長度（用於校準測量）")
        print("按 'q' 退出")

        while True:
            key = cv2.waitKey(1) & 0xFF
            if key == ord('q'):
                break
            elif key == ord('r'):
                if len(measurer.points) >= 2:
                    real_length = float(input("請輸入已知長度（公分）: "))
                    pixel_length = np.sqrt((measurer.points[1][0] - measurer.points[0][0]) ** 2 +
                                           (measurer.points[1][1] - measurer.points[0][1]) ** 2)
                    measurer.set_reference(pixel_length, real_length)
                else:
                    print("請先點選已知長度的兩個點")

        cv2.destroyAllWindows()
    else:
        print("圖片處理失敗")


if __name__ == "__main__":
    main()
