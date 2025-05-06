package main

import (
	"encoding/json"
	"fmt"
	"log"
	"net/http"
	"time"
)

// User represents a user in the system
type User struct {
	ID        string    `json:"id"`
	Name      string    `json:"name"`
	Email     string    `json:"email"`
	CreatedAt time.Time `json:"created_at"`
}

// UserService handles user operations
type UserService struct {
	users map[string]User
}

// NewUserService creates a new UserService
func NewUserService() *UserService {
	return &UserService{
		users: make(map[string]User),
	}
}

// CreateUser adds a new user
func (s *UserService) CreateUser(user User) error {
	if user.ID == "" {
		return fmt.Errorf("user ID cannot be empty")
	}
	s.users[user.ID] = user
	return nil
}

// GetUser retrieves a user by ID
func (s *UserService) GetUser(id string) (User, error) {
	user, exists := s.users[id]
	if !exists {
		return User{}, fmt.Errorf("user not found")
	}
	return user, nil
}

func main() {
	userService := NewUserService()

	http.HandleFunc("/health", func(w http.ResponseWriter, r *http.Request) {
		json.NewEncoder(w).Encode(map[string]string{
			"status":    "healthy",
			"timestamp": time.Now().Format(time.RFC3339),
		})
	})

	log.Println("Server starting on :8080")
	log.Fatal(http.ListenAndServe(":8080", nil))
}
