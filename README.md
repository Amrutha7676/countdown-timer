# countdown-timer
import time

def start_timer(duration_in_seconds):
    try:
        while duration_in_seconds > 0:
           
            minutes = duration_in_seconds // 60
            seconds = duration_in_seconds % 60
            
            timer_display = f"{minutes:02}:{seconds:02}"
            
            print("\033[H\033[J", end="")  
            print(f"Time left: {timer_display}", end="\r")
            
            time.sleep(1)
             
            duration_in_seconds -= 1
        
        print("\n00:00\nTime's up! You've completed your countdown.")
    
    except KeyboardInterrupt:
        print("\nTimer has been stopped manually. Goodbye!")

if __name__ == "__main__":
    try:
      
        total_time = int(input("Please enter the countdown duration in seconds: "))
        start_timer(total_time)
    
    except ValueError:
        print("Invalid input! Please enter a valid integer.")

           
